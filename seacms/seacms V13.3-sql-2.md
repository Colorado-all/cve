Seacms V13.3 has an SQL injection vulnerability that allows an authenticated attacker to exploit the database.

Download address：https://www.seacms.com/download/



![image-20250114112555007](images/image-20250114112555007.png)



The vulnerability is located in the admin_paylog.php file, starting from line 10, first check whether the value of the '$action' variable is equal to 'add', if so, get the values of 'num' and 'limit' from the POST request, go down to line 17, construct a 'key' value, It consists of $limit, a dash, and an md5 hash of the MD5 value generated in the previous step. Line 18 constructs an SQL insert statement to insert the newly generated key, limit, current time (NOW()), and some other default values into the sea_cck table. Here directly manipulate the database table, and do not limit, use 'to close the limit parameter, resulting in SQL injection problems.

![image-20250114135449068](images/image-20250114135449068.png)





```
POST /seacms/admin/admin_paylog.php?action=add HTTP/1.1
Host: 192.168.1.6
Content-Length: 46
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.1.6
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.60 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.1.6/seacms/admin/admin_pay.php?action=search
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=m71vec04rhrtoupojs9cei6lh6; mnm_user=admin; mnm_key=YWRtaW46MjJrTkdHVDVLbG9NWTphNDY0YTFkMTcxNzcxMWYxYmMwOWYxYjM3ZjU2ODMxOQ%3D%3D
Connection: close

num=10&limit=100&selectBtn=%E7%94%9F+%E6%88%90
```









![image-20250112210206974](images/image-20250112210206974.png)










