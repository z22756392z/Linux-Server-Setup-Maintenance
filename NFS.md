## Network File System

unix-like



For example , there are two machine;

machine one, we assume it is nfs server

machine two, we assume it is client

In machine one , we can export myData

In machine two, we can mount , mount to local directory.

When we create new file in myData, both machine can see it.

----

nfs server

client 1:

export : mydata(data to be shared)

client 2:

mount : mydata

---

在nfs server上的mydata 資料夾 就像是在 client2 上的資料夾一樣

(真正存放在 nfs server : like windows上的遠端磁碟機)



When data is exported, they can have many nfs client to mount this data.



## TO USE NFS

download server:

`yum install nfs-utils`

查詢電腦裡有沒有裝什麼東西

`rpm -qa | grep nfs`

`rpm -qa | grep rpcbin`

自動啟動 NFS

`sudo systemctl enable rpcbind`

`sudo systemctl enable nfs`

啟動服務

`sudo systemctl start rpcbind`

`sudo systemctl start nfs`

打開防火牆對nfs的服務

`sudo firewall-cmd --zone=public --pen`

`sudo firewall-cmd --reload`

創要共用的資料夾

`mkdir /newdir -p` : `-p` 如果有同樣的資料夾 不要建 有 反之

`sudo chmod 755 /newdir` : change the permission for directory

tell other machine here we have a folder to be shared by others

`sudo geditor /etc/exports`

`/newdir/ your ip./24(rw,sync,no_root_squash,no_all_squash)`

重啟伺服器 當設定改變

`sudo system restart nfs`

顯示有沒有分享成功

`showmount -e your_ip`

掛到本地端的`/newdir/test`

`mount -t nfs your_ip:/newdir/test` : `-t` 什麼類型



