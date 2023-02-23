# Sales Tracker Management System has SQL injection

BUG_Author: Murasaki

URL: 

* /php-sts/admin/clients/view_client.php?id=*
* /php-sts/admin/?page=user/manage_user&id=*

Parameter "id" (GET), exists SQL injection vulnerability

Link:https://www.sourcecodester.com/php/16061/sales-tracker-management-system-using-php-free-source-code.html


There are two SQL injection vulnerabilities in the Sales Tracker Management System. 

The system has a SQL injection vulnerability in the place where the user information is browsed and edited. The currentDB can be obtained by using the administrator privilege data package for testing.

The contents of the two data packs are as follows

```
GET /php-sts/admin/?page=user/manage_user&id=2 HTTP/1.1
Host: 192.168.8.131
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.8.131/php-sts/admin/?page=user/list
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=laneat1rjdrp0f6su5o6955b36
Connection: close
```



```
GET /php-sts/admin/clients/view_client.php?id=4 HTTP/1.1
Host: 192.168.8.131
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36
X-Requested-With: XMLHttpRequest
Referer: http://192.168.8.131/php-sts/admin/?page=clients
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=laneat1rjdrp0f6su5o6955b36
Connection: close
```

The URLs of the two detections are not the same
![](https://github.com/1MurasaKi/STMS_SQLi/blob/main/manager_user.png?raw=true)
![](https://github.com/1MurasaKi/STMS_SQLi/blob/main/view_client.png?raw=true)
