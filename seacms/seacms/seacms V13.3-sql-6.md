Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/



![image-20250114112532792](images/image-20250114112532792.png)



The vulnerability is located in the admin_collect_news.php file, starting at line 479, if the value of '$action' is' customersavecls' and the $e_id option exists, then proceed further. You can see that 488 gets the class name 'clsname' and the system class ID 'tid' from the POST request, and further down, if the class name is not empty, constructs and executes an SQL update statement, Update the new class name 'clsname' and system class ID 'tid' to the corresponding record in the database's 'sea_co_cls' table. There are SQL statement concatenation in this code, and there are controllable parameters, which can cause SQL injection problems.



![image-20250114142050259](images/image-20250114142050259.png)



```
POST /seacms/bf6nbn/admin_collect_news.php?action=customersavecls HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Referer: http://192.168.80.152/seacms/bf6nbn/admin_collect_news.php?action=customercls
Cookie: PHPSESSID=s5fhh9q24e7k8rjpi28g6o3j40; t00ls=e54285de394c4207cd521213cebab040; t00ls_s=YTozOntzOjQ6InVzZXIiO3M6MTA6InBocCB8IHBocD8iO3M6MzoiYWxsIjtpOjA7czozOiJodGEiO2k6MTt9
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 114

e_id%5B%5D=10&clsname10=1&tid10=17&Submit=%E6%89%B9%E9%87%8F%E4%BF%AE%E6%94%B9%E9%80%89%E4%B8%AD%E5%88%86%E7%B1%BB
```



![image-20250114035211404](images/image-20250114035211404.png)
