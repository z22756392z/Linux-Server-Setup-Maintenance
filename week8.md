## Command

`man command`: read manel

`cut -d ',' -f 2 doc4` : 分割符號是','

`cut -d ',' -f 1,3 doc4 | tr "," " " | sort -n -k 2 -r `: `sort`  `-n`: 數字`-k`: 排列第二欄`-r`:reverse (從大到小) 

`cut -d ',' -f 1,3 doc4 | sort -g -k 2 -t ","`: `sort` `-t` : separacter的是`,` 

`echo "123456789" | cut -c 2-5 `: 2345

`cat 1.txt 2.txt 3.txt > 4.txt`: combing 1,2,3 file to 4 file

`dd if=/dev/zero of=3M count = 3 bs1M`: 生3個 1M0的file

`split -b 1m 3M`: 分割 3M的file 分成3個1M (還原:`cat 1.txt 2.txt 3.txt > 4.txt`)

`echo $RANDOM | md5sum | cut -c 1-5`: 產生固定五位亂數

`read -p "input a number " nol`  :`-p`:接提示符號, `nol`:讀到的輸入放到nol

`[ -d fileName ] && echo "1" || echo "0"` :  `-d` 測試是否為 file 或是 directory`&&`前面執行成功 執行緊接著的 `||`前面執行失敗 執行緊接著的

`[ -d fileName ] && echo "1" || echo "0"` : `-e` 檔案是否存在

```bash
a = ""
[ -n $a ] && echo "1" || echo "0" (X)
[ -n "$a" ] && echo "1" || echo "0" (O)
//-n 是否為字串長度大於0
//-z 是否字串為空
```

```
a = "abc"
b = "abcd"
[ $a = $b ] && echo "echo" || echo "0"
//判斷是否變數一樣 -eq
// -le : less than or equal to
// -lt : less than
// ge : greater than or equal to
// gt : greater than
```

```
a=5
b=10
c=`expr $a + $b`
c=$(expr $a + $b)
//以上兩個 指令是一樣的 $a 與 $b 的空白要注意
c=$(expr $a /* $b)
//因為*是特殊符號 需要用 `/` 
```





## Script

注意空白 if 裡[ ]的前後 

```bash
#!/usr/bin/bash

if [ $UID -eq 0 ]; then
        echo "you are root"
else
        echo "you are normal user"
fi

```

