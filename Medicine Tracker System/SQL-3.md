

The Medicine Tracker System has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/16308/medicine-tracker-system-php-oop-and-mysql-db-source-code-free-download.html



The vulnerability is located in the /app/medicines/view_details.php file. You can see that there is a direct concatenation of SQL statements and parameters in the code snippet.

![image-20250326222843583](images/image-20250326222843583.png)



Vulnerability verification：

```
GET /php-mts/app/medicines/view_details.php?id=1 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive


```

 ![image-20250326222852598](images/image-20250326222852598.png)



































