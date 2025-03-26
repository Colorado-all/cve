



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/action/edit_suppliar.php file, where you can see an action to update the information in the code snippet.

![image-20250326143931826](images/image-20250326143931826.png)





Vulnerability verification：

```
POST /ample/app/action/edit_suppliar.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie: PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 63

id=1&name=1&designation=1&contact=1&email=1&address=1&company=1
```

 ![image-20250326143855181](images/image-20250326143855181.png)



































