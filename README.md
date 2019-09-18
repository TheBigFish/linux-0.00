# linux-0.00

## 运行环境
bochs: 2.6.9
ubuntu: 16.04

## 源码下载

[linux-0.00-050613.zip](http://oldlinux.org/Linux.old/bochs/)

解压 `linux-0.00-rh9.tar.gz`

## 源码修改

head.s  
第九行增加 `.code32`

Makefile
第四行改为 `AS	=as --32`

新增 bochsrc-0.00.bxrc,内容为：
```
romimage: file=$BXSHARE/BIOS-bochs-latest
vgaromimage: file=$BXSHARE/VGABIOS-lgpl-latest
megs: 16
floppya: 1_44="Image", status=inserted
boot: a
log: bochsout.txt
```
## 编译
sudo apt-get install bin86
make

## 运行
bochs -f bochsrc-0.00.bxrc
回车
c

