



The Free and Open Source inventory management system has an SQL injection vulnerability that an attacker, if authenticated, can exploit to steal information or corrupt a database.





Source code address：https://www.sourcecodester.com/php/16741/free-and-open-source-inventory-management-system-php-source-code.html



The vulnerability is located in the /app/action/edit_purchase.php file, where an operation to update the information can be seen in the code snippet.

![image-20250326144204580](images/image-20250326144204580.png)

![image-20250326144219600](images/image-20250326144219600.png)



Vulnerability verification：

```
POST /ample/app/action/edit_purchase.php HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Cookie:  PHPSESSID=c4gam437gl7cc6hlbsgm3pplq4
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 227

edit_id=1&p_supliar=1&puchar_date=1&p_product_name=1&product_id=1&p_p_quantity=1&p_pn_quantity=1&this_buy_qnty=1&p_p_price=1&p_p_sell_price=1&p_subtotal=1&p_discount_amount=1&p_netTotal=1&p_paidBill=1&p_dueBill=1&p_payMethode=1
```

 ![image-20250326144059700](images/image-20250326144059700.png)



































