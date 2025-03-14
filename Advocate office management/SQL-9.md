

Advocate office management has an SQL injection vulnerability that could be exploited by an attacker to steal information or compromise a database without authentication.





Source code address：https://www.sourcecodester.com/php/17280/advocate-office-management-system-free-download.html



The vulnerability is located in the /control/addcase_stage.php file, you can see that the code is the add and cname parameters for receiving POST requests, and then look at the cname parameter exists and the SQL statement is concatenated.

![image-20250314121019899](images/image-20250314121019899.png)



Vulnerability verification：

```
POST /office/kortex_lite/control/addcase_stage.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 5

add=1&cname=1
```

![image-20250314120957888](images/image-20250314120957888.png)



































