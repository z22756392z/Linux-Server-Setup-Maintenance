磁碟空間分配

## Enter single user mode

F10



`vi /etc/fstab`

![image-20220926134204715](/img/image-20220926134204715.png)



after reboot vm

![image-20220926134316879](/img/image-20220926134316879.png)



磁碟配置

centos -- xfs

`xfs-quota -xc 'report -h' /home`



Used: how many space you use

Soft: when you exit soft limit it will give you some warning message

Hard: hard is the upper limit you can't excess (0 mean There's no limit)

![image-20220926134747425](/img/image-20220926134747425.png)



![image-20220926134823378](/img/image-20220926134823378.png)

![image-20220926135203576](/img/image-20220926135203576.png)

`xfs_quota -xc "limit bsoft=10m bhard=12m user" /home` 

設定使用者home資料量

![image-20220926135208481](.\img\image-20220926135208481.png)

`dd if=/dev/zero of test bs=1M count=13`

`dd`: 產生特定大小的指令

generate a specific size file 

`if` :mean input file `/dev/zero` 

`bs`: 每次到1M

`count`: 13次

因為輸入了13次 有13M 但限制了使用者量12M 超過所以會產生錯誤

![image-20220926135816261](/img/image-20220926135816261.png)