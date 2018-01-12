# 存储管理
主要描述从内存到磁盘等存储介质的管理，包括了（考点）**内存管理、地址映射、内存保护、内存扩充**

## <codepub>存储器的层次</codepub>
1. CPU寄存器
2. CPU高速缓存
2. 主机RAM/ROM主存
3. 辅存：闪存等
5. 外存：磁盘

## 内存在计算机系统中的地位
![](http://upload-images.jianshu.io/upload_images/4925817-5ce45b626021be03.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

程序装入内存的方式（主要阶段详见编译原理）
- 绝对装入方式
- 可重定位装入方式
- 动态运行时装入方式

## <codepub>重定位</codepub>
<codepub>程序和数据装入内存时，需对目标程序中的地址进行修改映射，这种把逻辑地址转变为内存物理地址的过程称作重定位</codepub>
  - <codepub>静态重定位：目标程序装入内存时进行地质变换，运行期间不允许转移或申请新的空间</codepub>
  - <codepub>动态重定位：程序执行期间允许重新转换地质，允许申请新的空间和根据需要进行转址。需要硬件地址转换机构</codepub>