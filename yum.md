redhat/fedora/centos : rpm/yum   debian/ubuntu: dpkg/apt



rpm : software package manager已經編譯好 , 也已經把檔案放在對應的位置

`rpm -qa | grep httpd`

`rpm -qa`: list all package that has installed in the system

`rpm -ql httpd` : quarry list

![image-20220926145935109](/img/image-20220926145935109.png)

yum -- 解決依賴性 而 rpm沒有

![image-20220926150733703](/img/image-20220926150733703.png)

https://rpmfind.net/linux/epel/7/x86_64/Packages/j/joe-4.6-4.el7.x86_64.rpm

https://src.fedoraproject.org/lookaside/extras/htop/htop-2.2.0.tar.gz/sha512/ec1335bf0e3e0387e5e50acbc508d0effad19c4bc1ac312419dc97b82901f4819600d6f87a91668f39d429536d17304d4b14634426a06bec2ecd09df24adc62e/htop-2.2.0.tar.gz