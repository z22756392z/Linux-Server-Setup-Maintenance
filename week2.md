[NFS](./NFS.txt)

## Backup

tar包 : 把檔案與目錄統一包成一個檔案 (.tar)

 打包並壓縮過(.tar.gz == .tgz)

[GNU / Linux 各種壓縮與解壓縮指令 (drx.tw)](http://note.drx.tw/2008/04/command.html)

Folders that need to Backup

`/etc`: ip name, route, host name(`/etc/hostname`),server setting(dns server: `/etc/resolv.conf`), 手動配置網路卡設定(`/etc/sysconfig/network-scripts/`),

 `/home`:

`/var/spool`:

打包

`tar -cvfz etc- 'data +"%Y-%m-%d"' .tar.gz /etc`

ex: etc-2022-09-12.tar.gz

## Time setting

`timedatectl set-timezone Asia/Taipei` : set timezone

## Crontab

[Linux 設定 crontab 例行性工作排程教學與範例 - G. T. Wang (gtwang.org)](https://blog.gtwang.org/linux/linux-crontab-cron-job-tutorial-and-examples/)

寫執行命令要寫完整路徑(絕對路徑)

crontab 格式:

| 欄位 | 說明             | 可設定的值                                                   |
| :--- | :--------------- | :----------------------------------------------------------- |
| MIN  | 分鐘             | `0` 到 `59`                                                  |
| HOUR | 小時             | `0` 到 `23`                                                  |
| DOM  | 日               | `1` 到 `31`                                                  |
| MON  | 月份             | `1` 到 `12`，此欄位亦可用英文簡稱取代，例如一月也可以寫 `Jan`。 |
| DOW  | 星期幾           | `0`（週日）到 `6`（週六），`7` 也代表週日。此欄位亦可用英文簡稱取代，例如週日也可以寫 `Sun`。 |
| CMD  | 要定期執行的指令 | 任何可執行的程式或指令稿（包含參數），例如 `/path/to/cmd --your --parameter`。 |

| 特殊字元           | 代表意義                                                     |
| :----------------- | :----------------------------------------------------------- |
| 星號（`*`）        | 代表接受任意時刻，例如若在月份那一欄填入星號，則代表任一月份皆可。 |
| 逗號（`,`）        | 分隔多個不同時間點。例如若要指定 3:00、6:00 與 9:00 三個時間點執行指令，就可以在第二欄填入 `3,6,9`。 |
| 減號（`-`）        | 代表一段時間區間，例如若在第二欄填入 `8-12` 就代表從 8 點到 12 點的意思，也就是等同於 `8,9,10,11,12`。 |
| 斜線加數字（`/n`） | n 代表數字，這樣寫的意思就是「每隔 n 的單位」的意思，例如若在第一欄填入 `*/5` 就代表每間隔五分鐘執行一次的意思，也可以寫成 `0-59/5`。 |

8月 15日 9點30分

30 09 15 08 *

![image-20220912161559432](/img/image-20220912161559432.png)

## Command

`file TargetFile`: use `file` to know the file type 

`stat TargetFile`: know the file detail:  inode, size, modify time...

`find / -atime -1`: find accessed file

`mkdir {a,b,c,d}` : make mutliple directory

`tar cvf test.tar test`: c: create v:verbose  f:file name

`tar zcvf test.tar.gz test`: z: compression(use gzip/gunzip),c: create, v:verbose, f:file name

`tar xzvf myfile.tagz` : 解壓縮(.tgz)

`tar xvf myfile.tagz` : 解壓縮(.tar)

`zip -r testfile.zip testfile` : 輸出.zip檔案 可以丟到windows 