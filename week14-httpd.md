## SELinux



## Httpd

centos

`/etc/httpd`: settings

​	`conf,conf.d,conf.modules.d,logs modules,run`

​	`http.conf`

​		增加pid![image-20221205145402386](/img/image-20221205145402386.png)

​		客戶預設的ip的回傳資源(index.html)

![image-20221205150158397](/img/image-20221205150158397.png)

​	`userdir.conf`

​		每個使用者有自己www 網站![image-20221205150527590](/img/image-20221205150527590.png)

​	設定完後在 要有自己的網站的user資料夾下創造 public_html資料夾 在創造新的html

​	並把改變使用者權限 `chmod 755 /home/user` 讓public_html裡的html可以被存取

​	用`ip/~userid/..htm` ex:`192.168.56.101/~z22756392z/hi.htm`連線

`/var/www/html`: home directory

`/var/log/httpd/`: log

​	`	access_log`:

```
192.168.56.1 - - [05/Dec/2022:01:32:31 -0500] "GET /web.htm HTTP/1.1" 304 - "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36 Edg/107.0.1418.62"

192.168.56.1 - - 是否跳轉 或是 直接到這個ip
GET 客戶端從伺服器拿的資源 /web.htm
HTTP/1.1 協定
	2.. 開頭成功
	3.. 跳轉
	4.. 錯誤
	5.. 客戶端操作造成問題
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36 Edg/107.0.1418.62  客戶端使用的
	可以依據這個資訊跳轉到合適的網頁(電腦,手機...)

```

​		利用這個access_log可得到許多資訊

​		得到有多少不同ip存取過這個網站 

​		`cat /var/log/httpd/access_log | awk '{print $1}' | sort | uniq`

​		出現錯誤的有多少筆,昨天到今天的存取數,用dns分析ip得到ip從哪個國家來...

​	`error_log`:認證失敗



ubuntu

`/usr/local/apache2/htdocs/`



## Virtual host

two server in same ip,same port

how to distinguish?

4 -> application layer address (virtual host address[in httpd protocol])

usage: www, ftp

## Load balancer(LB)

![image-20221205141038127](/img/image-20221205141038127.png)

high pressure

L4: 根據ip,tcp進行轉發到不同伺服器

L7:根據www.a.com,www.b.com(url)進行轉發

Cluster

LB: LVS,haproxy,nginx

## website

how to let website acess file except `var/www/html`

1. 創造連結在`var/www/html`之中   `ln -s /directory`

2. 設定檔 Aliases (創造別名) 在/etc/httpd/conf/httpd.conf

   ![image-20221205161303716](/img/image-20221205161303716.png)

   `Alias /alias_data /alias_data` 第一個`/alias_data` 代表httpd中的名稱 第二個代表位置

## Command

`rpm -qa | grep httpd`: check if installed

`tail -f access_log`: `-f`:(follow)追蹤access_log這個檔案 

`ntpdate clock.stdtime.gov.tw`:時間同步

`ln -s /directory`: 建立符號連結