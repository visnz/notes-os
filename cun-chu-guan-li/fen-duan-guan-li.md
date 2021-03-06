# 分段管理技术
是一组逻辑信息的集合，每段都有自己的名字、长度、段号（内存管理）
逻辑地址要用两个成分来表示：段号s和段内地址d，来指向一个数据的地址
![](https://gss0.bdstatic.com/94o3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike72%2C5%2C5%2C72%2C24/sign=b87301b265380cd7f213aabfc02dc651/8694a4c27d1ed21b06f9d0e7ad6eddc451da3ffb.jpg)

并由此来完成从逻辑地址到物理地址的转换工作，使得内存分配更加可调度，信息保护、动态增长与链接更为容易


通常会使用地址转换机构进行转换
![](https://gss3.bdstatic.com/-Po3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike92%2C5%2C5%2C92%2C30/sign=a7bbfbefa3cc7cd9ee203c8b58684a5a/d1160924ab18972bdf13e0c8e6cd7b899e510a82.jpg)

## 分段
> 在分段存储管理方式中，作业的地址空间被划分为若干个段，每个段定义了一组逻辑信息。每个段都有自己的名字。为了实现简单起见，通常可用一个段号来代替段名，每个段都从0开始编址，并采用一段连续的地址空间。段的长度由相应的逻辑信息组的长度决定，因而各段长度不等。整个作业的地址空间由于是分成多个段，因而是二维的，亦即，其逻辑地址由段号(段名)和段内地址所组成。

## 段表
在分段式存储管理系统中，为每个分段分配一个连续的分区，而进程中的各个段可以离散地移入内存中不同的分区中。为使程序能正常运行，亦即，能从物理内存中找出每个逻辑段所对应的位置，应像分页系统那样，在系统中为每个进程建立一张段映射表，简称“段表”。
![](https://gss0.bdstatic.com/-4o3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike92%2C5%2C5%2C92%2C30/sign=7e1b97246d224f4a43947b41689efb37/5fdf8db1cb134954c5c30966564e9258d0094ad7.jpg)



## 分页分段区别
1. <codepub>页是信息的物理单位，段是信息的逻辑单位</codepub>
2. <codepub>页的大小是由系统确定的，段的长度因段而异</codepub>
3. <codepub>分页的进程地址空间是一维的，分段的进程地址空间是二维的</codepub>
4. <codepub>分页系统很难实现过程和数据的分离，分段系统却可以很容易实现这些功能</codepub>

> 部分内容与图片引用来自百度百科：https://baike.baidu.com/item/%E5%9F%BA%E6%9C%AC%E5%88%86%E6%AE%B5%E5%AD%98%E5%82%A8%E7%AE%A1%E7%90%86%E6%96%B9%E5%BC%8F