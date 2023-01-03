[pptpd](./server_hosting_pptpd.txt)

## Command

* `ssh root@centos7-2 ifconfig`: `ssh root@centos7-2`:normally it mean login to centos7-2, but if you add some command after it, you execute those command in centos7-2 computer

* `scp` : copy file

  * `scp 1.txt root@centos7-2:/tmp` copy 1.txt to centos7-2 tmp directory

  * `scp root@centos7-2:/tmp/1.txt /tmp/aa.txt` copy file from centos7-2 to local

  *  `scp -r test root@centos7-2:/tmp` `-r` mean recursively copy file from directory

* `seq`: print out sequence of number, `seq startVal [increment] endVal` `[]` mean optional default value is 1. 
  * `seq -w 3 1 1 10` `-w` result has the same width
  * `seq -s + 1 5` `-s`用...連起來 這裡是加號

![image-20221017150213096](/img/image-20221017150213096.png)

![image-20221017150522797](/img/image-20221017150522797.png)

* `bc`: floating point calculation type the expression and using the pipe to throw it bc , it will give you the result

  * `seq -s + 1 5 | bc` 

    ![image-20221017150644621](.\img\image-20221017150644621.png)

![image-20221017151715287](/img/image-20221017151715287.png)

* `sort` : result will show from `a-z` to `A-Z` , if first character is the same , it will continue to compare next character until end

  ![image-20221017154828621](.\img\image-20221017154828621.png)

* `uniq`:  put all the same then execute uniq,  

![image-20221017155022289](/img/image-20221017155022289.png)



* `cut -d  "," -f 2 doc4`, `awk -F, '{print &2}' doc4`

#### 數據統計

111.222.333.123這個ip 造訪多少次網站

![image-20221017160615910](/img/image-20221017160615910.png)

有多少不同的ip 造訪網站

![image-20221017160908850](/img/image-20221017160908850.png)