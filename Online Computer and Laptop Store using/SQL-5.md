

Online Computer and Laptop Store using an SQL injection vulnerability can be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/16397/online-computer-and-laptop-store-using-php-and-mysql-source-code-free-download.html



The vulnerability is located in the /admin/sales/index.php file, and in the code snippet you can see that the parameters passed in are concatenated directly with the SQL statement.

![image-20250326230231213](images/image-20250326230231213.png)

![image-20250326230242690](images/image-20250326230242690.png)

Vulnerability verification：

```
GET /php-ocls/admin/?page=sales&date_start=2025-02-26&date_end=2025-03-05 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive


```

 ![image-20250326230117607](images/image-20250326230117607.png)



































