

Advocate office management has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/17280/advocate-office-management-system-free-download.html



The vulnerability is located in the /control/deactivate.php file, and you can see that the code is the id parameter that receives the GET request and is assigned to the $uid and then directly brought into the database for operation.

![image-20250314121703344](images/image-20250314121703344.png)



Vulnerability verification：

```
GET /office/kortex_lite/control/deactivate.php?id=1 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
```

![image-20250314121715771](images/image-20250314121715771.png)



































