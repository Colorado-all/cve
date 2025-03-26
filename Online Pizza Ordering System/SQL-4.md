

The Online Pizza Ordering System has an SQL injection vulnerability, which can be exploited by an attacker to steal information or corrupt a database without authentication.



Source code address：https://www.sourcecodester.com/php/16166/online-pizza-ordering-system-php-free-source-code.html



The vulnerability is located in save_category in the /admin/ajax.php file, and you can see in the code snippet that the parameters passed in are concatenated directly with the SQL statement.

![image-20250326231429113](images/image-20250326231429113.png)



Vulnerability verification：

```
POST /php-opos/admin/ajax.php?action=save_category HTTP/1.1
Host: 192.168.80.152
Content-Length: 225
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36
Accept: */*
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryBUDLbwlTuoLeQTmu
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

------WebKitFormBoundaryBUDLbwlTuoLeQTmu
Content-Disposition: form-data; name="id"


------WebKitFormBoundaryBUDLbwlTuoLeQTmu
Content-Disposition: form-data; name="name"

1
------WebKitFormBoundaryBUDLbwlTuoLeQTmu--

```

 ![image-20250326231413445](images/image-20250326231413445.png)



































