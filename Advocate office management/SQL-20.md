

Advocate office management has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/17280/advocate-office-management-system-free-download.html



The vulnerability is located in the /control/log.php file, you can see that the code is to receive the POST request username, password parameters, down to 26 lines, will put the input content into the SQL statement for query, resulting in direct splicing.

![image-20250314122730195](images/image-20250314122730195.png)



Vulnerability verification：

```
POST /office/kortex_lite/control/log.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
Content-Type: multipart/form-data; boundary=---------------------------19549232618174
Content-Length: 352

-----------------------------19549232618174
Content-Disposition: form-data; name="username"

1@qq.com
-----------------------------19549232618174
Content-Disposition: form-data; name="password"

1
-----------------------------19549232618174
Content-Disposition: form-data; name="login"

Login
-----------------------------19549232618174--

```

![image-20250314122905933](images/image-20250314122905933.png)



































