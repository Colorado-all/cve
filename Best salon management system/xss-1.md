



The Best salon management system has an xss vulnerability. Attackers, after authentication, exploit this vulnerability to affect the system's functionality.



Source code address：https://www.sourcecodester.com/php/18171/best-salon-management-system-project-php.html



Vulnerability path：  /barbarbaba/panel/edit-customer-detailed.php 。





Vulnerability verification：

```
"><svg onload=alert(1)>//
```

 

![image-20250621123013058](images/image-20250621123013058.png)



![image-20250621123018311](images/image-20250621123018311.png)

![image-20250621123023602](images/image-20250621123023602.png)



























