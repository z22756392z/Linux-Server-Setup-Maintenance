[CentOS7搭建ftp服务器实现匿名上传下载_zhaojia92的博客-CSDN博客_centos7 ftp 上传下载](https://blog.csdn.net/zhaojia92/article/details/79511581)

`rpm -qa | grep vsftpd`

`yum install vsftpd`

`/var/ftp` 家目錄 default home directory

`/var/ftp/public` 

`netstat -tunlp | grep 21 check if ftp started` ==> no => `systemctl start vsftpd`

## permission deny

`/var/ftp/public`: `chmod 777 /var/ftp/public`, `chmod 777 /var/ftp` or `chmod -R /var/ftp`

if all failed:check config file

`/etc/vsftpd/`

inside vsftpd.conf : `anon_upload_enable=Yes` ,`anon_mkdir_write_enable=Yes`,`anon`uncomment



if all failed:[CentOS7搭建ftp服务器实现匿名上传下载_zhaojia92的博客-CSDN博客_centos7 ftp 上传下载](https://blog.csdn.net/zhaojia92/article/details/79511581)

[note/2021_12_13.md at master · FUYUHSUAN/note (github.com)](https://github.com/FUYUHSUAN/note/blob/master/110-伺服器架設/W10/2021_12_13.md)





system account and pwd : can go to home directory