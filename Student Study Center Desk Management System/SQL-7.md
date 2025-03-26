The Student Study Center Desk Management System has an SQL injection vulnerability that could be exploited by an attacker to steal information or corrupt a database without authentication.







Source code address：https://www.sourcecodester.com/php/16298/student-study-center-desk-management-system-using-php-oop-and-mysql-db-free-source-code



The vulnerability is located in the /admin/students/view_student.php file, and it can be seen in the code snippet that the passed parameter has the behavior of directly concatenating with the SQL statement.

![image-20250326235736863](images/image-20250326235736863.png)



Vulnerability verification：

```
GET /php-sscdms/admin/?page=students/view_student&id=3 HTTP/1.1
Host: 192.168.80.152
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
DNT: 1
Connection: keep-alive


```

 ![image-20250326235548178](images/image-20250326235548178.png)



































