



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/ajax/expense_data.php file, and you can see the concatenation of SQL statements in the code snippet.

![image-20250326145347273](images/image-20250326145347273.png)





Vulnerability verification：

```
POST /ample/app/ajax/expense_data.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie:  PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 318

draw=3&start=20&length=10&order[0][column]=2&order[0][dir]=desc&columns[0][data]=id&columns[0][searchable]=true&columns[0][orderable]=true&columns[1][data]=name&columns[1][searchable]=true&columns[1][orderable]=true&columns[2][data]=created_at&columns[2][searchable]=false&columns[2][orderable]=true&search[value]=john
```

 ![image-20250326145318050](images/image-20250326145318050.png)



































