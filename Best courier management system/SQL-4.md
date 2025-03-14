

The Best courier management system has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.



Source code address：https://www.sourcecodester.com/php/16848/best-courier-management-system-project-php.html



The vulnerability is located in the view_parcel.php file, it can be seen that the third line of code directly receives the submitted GET request information and directly concatenates with the SQL statement, there is no restriction here, and there is a security risk.

![image-20250314141125627](images/image-20250314141125627.png)



Vulnerability verification：

```
GET /courier/view_parcel.php?id=166 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
X-Requested-With: XMLHttpRequest
Connection: keep-alive


```

![image-20250314141057519](images/image-20250314141057519.png)





































