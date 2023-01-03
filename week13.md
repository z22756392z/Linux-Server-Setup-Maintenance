## LAMP

[Centos7 LAMP環境建置(Linux,Apache,MySQL, PHP) - TWIDC LAB](https://lab.twidc.net/lamplinuxapachemysql-php-centos7/)

Linux,Apache,MySQL,PHP



--MariaDB

`mysql -u root -p`: login

`show databases;`

`create database testdb;`

`use testdb;`

`create table TableName(name varchar(50) not null, phone char(10));`

![image-20221128142308088](/img/image-20221128142308088.png)

`insert into TableName(attribute1,attribute2..) values(value1,value2,...);`

[[MySQL\] 心得筆記(4) Table 的新增、修改、刪除 - Clay-Technology World (clay-atlas.com)](https://clay-atlas.com/blog/2019/11/21/sql-table-create-insert-update-remove-delete/)

![image-20221128151925623](/img/image-20221128151925623.png)



```
$sql="select name, phone from TableName";
$result = $conn->query($sql);

if($result->num_rows > 0){
        while($row = $result->fetch_assoc()){
                echo "name:".$row["name"]." phone: " $row["phone"]."<bar>";
        }
} else{
        echo "0 result";
}
?>

```

## Command

`netstat -tunlp | grep 8888` : 如果是空的代表這個port 沒有人占用

`systemctl enable httpd`:下次reboot自動開啟

`ps -aux | grep httpd`: find httpd's process

`ps -ajx | grep httpd`:  `j`會議id (session id) 

`kill -9 -s sessionID`: kill all this session's processes `-s` : session id