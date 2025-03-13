



AC Repair and Services System using SQL injection vulnerabilities can be exploited by attackers to steal information or corrupt databases without authentication.



Source code address：https://www.sourcecodester.com/php/16513/ac-repair-and-services-system-using-php-and-mysql-source-code-free-download.html



The vulnerability is located in the /services/view.php file, and from the following code, you can see that the GET request id parameter is directly carried into the post-SQL statement for concatenating the query.

![image-20250313220615293](/images/image-20250313220615293.png)



漏洞验证：

```
GET /php-acrss/?page=services/view&id=2 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive
```

![image-20250313221324836](/images/image-20250313221324836.png)





































