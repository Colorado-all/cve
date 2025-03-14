

Advocate office management has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/17280/advocate-office-management-system-free-download.html



The vulnerability is located in the /control/add_act.php file, you can see that the code is to receive the POST request add, aname parameters, and then look down the aname parameters exist and SQL statement concatenate.

![image-20250314120756595](images/image-20250314120756595.png)



Vulnerability verification：

```
POST /office/kortex_lite/control/add_act.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 5

add=1&aname=1
```

![image-20250314120725220](images/image-20250314120725220.png)



































