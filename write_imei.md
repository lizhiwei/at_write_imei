


## 获取root权限

使用Magisk

## 探测AT命令端口

1.开启第1个adb shell

    su
    cd /dev/pts
    cat 3

2.开启第2个adb shell

    su
    echo -e 'ATI\r'  > /dev/pts/3

3. 如果发现第1个adb shell 里有回应

    OK

    MTK2
    MOLY.LR9.W1444.MD.LWTG.MP.V42

说明，这是一个正确的AT命令了端口

不是，修改端口号， 从1到10, 一个一个地试

## 读取IMEI

第2个shell输入

    echo -e 'AT+EGMR=0,7\r'  > /dev/pts/3

第1个shell回应

    +EGMR: "357326091500213"
    OK


读第2个IMEI, 将选项从7改到10

   echo -e 'AT+EGMR=0,10\r' > /dev/pts/3  


## 写IMEI

    echo -e 'AT+EGMR=1,7,"357326091500213"\r'  > /dev/pts/3
    echo -e 'AT+EGMR=1,10,"357326091552222"\r'  > /dev/pts/3

这两个IMEI，可是国内行货 iPhone XS Max 256G 深空灰色 ， 保修至 2019年9月21日

##  验证设备

中兴Blade A1

联想K5s
