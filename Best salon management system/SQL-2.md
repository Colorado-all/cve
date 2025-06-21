



The Best salon management system has an SQL injection vulnerability. If an attacker is authenticated, they can exploit this vulnerability to steal information or damage the database.





Source code address：https://www.sourcecodester.com/php/18171/best-salon-management-system-project-php.html



The vulnerability is located in the barbarbaba/panel/add-customer.php file. The code receives the data submitted by the user and then writes it to the database. There is a direct concatenation with the SQL statement without too many restrictions, which poses a security risk.

![image-20250621115325833](images/image-20250621115325833.png)





Vulnerability verification：

```
POST /barbarbaba/panel/add-customer.php HTTP/1.1
Host: 192.168.80.152
Content-Length: 129
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.80.152
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.60 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.80.152/barbarbaba/panel/add-customer.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=9qunanken3a3eh5ub3i2aegl9i
Connection: close

name=mayuri&email=mayuri.infospace%40gmail.com&mobilenum=9861234589&dob=2025-05-31&marriage_date=2025-05-31&details=11111&submit=
```

 ![image-20250621115145763](images/image-20250621115145763.png)



































