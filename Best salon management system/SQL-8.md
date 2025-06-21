



The Best salon management system has an SQL injection vulnerability. If an attacker is authenticated, they can exploit this vulnerability to steal information or damage the database.





Source code address：https://www.sourcecodester.com/php/18171/best-salon-management-system-project-php.html



Loopholes in barbarbaba/panel/stock. PHP file, in the code to receive the user submits the data and then update the information in the database, there is a direct and joining together of SQL statements, didn't do too many restrictions, pose a safety hazard.

![image-20250621120859112](images/image-20250621120859112.png)



Vulnerability verification：

```
POST /barbarbaba/panel/stock.php HTTP/1.1
Host: 192.168.80.152
Content-Length: 50
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.80.152
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.60 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.80.152/barbarbaba/panel/manage-services.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=9qunanken3a3eh5ub3i2aegl9i
Connection: close

ID=11&opening_stock1=34&opening_stock=1111&submit=
```

 ![image-20250621120756275](images/image-20250621120756275.png)



































