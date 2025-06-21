



The Best salon management system has an xss vulnerability. Attackers, after authentication, exploit this vulnerability to affect the system's functionality.



Source code address：https://www.sourcecodester.com/php/18171/best-salon-management-system-project-php.html



Vulnerability path： /barbarbaba/panel/search-appointment.php 



Vulnerability verification：

```
<svg onload=alert(4)>//
```

 ![image-20250621123215556](images/image-20250621123215556.png)

![image-20250621123220219](images/image-20250621123220219.png)

































