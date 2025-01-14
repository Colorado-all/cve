Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/



![image-20250114112524682](images/image-20250114112524682.png)



The vulnerability is located in the admin_zyk.php file. Starting at line 41, if the value of '$action' is' edit 'and the $e_id option exists, then proceed further. Get the repository name 'zname', the repository API 'zapi', the repository information 'zinfo' and the repository type 'ztype' from the POST request in the body of the loop. If neither the repository name nor the repository API is empty, construct and execute an SQL update statement. Update the new field value to the corresponding record in the database's 'sea_zyk' table. As can be seen from line 65, there is concatenation of SQL statements, and the variables are controllable, which can cause SQL injection problems.



![image-20250114145327003](images/image-20250114145327003.png)





```
POST /seacms/51fek7/admin_zyk.php?action=edit HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Referer: http://192.168.80.152/seacms/51fek7/admin_zyk.php
Cookie: PHPSESSID=s5fhh9q24e7k8rjpi28g6o3j40; t00ls=e54285de394c4207cd521213cebab040; t00ls_s=YTozOntzOjQ6InVzZXIiO3M6MTA6InBocCB8IHBocD8iO3M6MzoiYWxsIjtpOjA7czozOiJodGEiO2k6MTt9
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 89

e_id%5B%5D=1&zid1=1&zname1=1&zapi1=1&zinfo1=%E6%9A%82%E6%97%A0%E6%8F%8F%E8%BF%B0&ztype1=1
```



![image-20250114111011890](images/image-20250114111011890.png)
