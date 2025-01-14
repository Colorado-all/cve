







Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/

![image-20250114112516349](images/image-20250114112516349.png)



The vulnerability is located in the admin_members.php file, starting from line 9, first check whether the value of the $ac variable is equal to 'search', if the value of $ac is 'search', then further check whether the search criteria are provided, and if the search criteria is empty, it will prompt an error message. If the search criterion exists, the code continues down to construct the SQL query statement, and if $uid is not empty, add it to the $wheresql string to construct the IN query criterion for the id. If $uname is not empty, use the str_replace() function to replace * with %, since % is used as a wildcard in SQL, and then add it to the $wheresql string to construct the LIKE query condition. Remove the and at the end of the $wheresql string, construct a complete SQL query, and execute the query using the $dsql object. After reading this code, it is almost enough to know that when building SQL queries, directly insert the variable ($uid) for query, and do not set the relevant filter conditions, use) closure can control the variable to cause SQL injection problems.



![image-20250114113159919](images/image-20250114113159919.png)







```
POST /seacms/51fek7/admin_members.php?ac=search HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Referer: http://192.168.80.152/seacms/51fek7/admin_members.php
Cookie: PHPSESSID=s5fhh9q24e7k8rjpi28g6o3j40; t00ls=e54285de394c4207cd521213cebab040; t00ls_s=YTozOntzOjQ6InVzZXIiO3M6MTA6InBocCB8IHBocD8iO3M6MzoiYWxsIjtpOjA7czozOiJodGEiO2k6MTt9
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 40

uname=1&uid=1&Submit=%E6%90%9C+%E7%B4%A2
```



![image-20250114110817890](images/image-20250114110817890.png)

