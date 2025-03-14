

The Best Employee management system has an SQL injection vulnerability that, after being authenticated, could be exploited by an attacker to steal information or compromise a database.





Source code address：https://www.sourcecodester.com/php/17689/best-employee-management-system-php.html



The vulnerability is located in the admin/ edit_role-php file. In this code, some files are introduced to check the user's login status and user information, receive the id parameters of POST requests submitted after authentication, and directly concatenate with SQL statements, which has potential security risks.

![image-20250314150943836](images/image-20250314150943836.png)



Vulnerability verification：

```
POST /employee/admin/edit_role.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie: PHPSESSID=323brna9jrc7c8eqaq5sdhnk65
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 4

id=1
```

![image-20250314150847653](images/image-20250314150847653.png)





































