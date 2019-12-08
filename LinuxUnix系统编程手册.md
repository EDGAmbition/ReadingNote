# 第二章 基本概念
## 2.7 进程
- 系统调用`execve()`可以加载或执行一个全新程序.
- 环境变量:使用`export`命令创建环境变量
    - 例子:`export MYVAR = 'hello world'`
## 2.8 内存映射
- 调用系统函数`mmap()`的进程,会在其虚拟地址空间中创建一个新的内存映射.
    - 映射分为两类:文件映射和匿名映射.
## 2.9 静态库和共享库
- 静态库(也称为archives),使用静态库编译的函数中会保存有静态库函数的副本.
- 共享库,在可执行文件中写入需要用到动态库的记录,`动态链接器`会找到动态库并载入内存.
## 2.12 线程
线程会共享统一数据区域和堆,但是会拥有自己的栈.

# 第三章 系统编程概念
## 系统调用的执行步骤
![syscall][1]
## 3.2,3.3 库函数
GNU C语言函数库glibc
# 第四章 文件IO:通用IO模型 p57
## 4.1 概述
打开:`fd = open(pathname,flags,mode)`
&emsp;读:`numread = read(fd,buffer,count)`
&emsp;写:`numwritten = write(fd,buffer,count)`
关闭:`status = close(fd)`
## 4.2 通用I/O
以上四个系统调用可以对所有类型的文件执行I/O操作,也包括终端设备.
```
./copy a.tet /dev/tty   // file -> terminal
./copy /dev/tty b.txt   // terminal -> file
```
### 目前4.2节







[1]:./fig/syscall.png
