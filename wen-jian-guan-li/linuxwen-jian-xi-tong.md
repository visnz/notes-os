# Linux文件系统

文件系统之上的硬盘分区：
  - <codepub>MBR分区</codepub>：
    - 分区表：在第一个扇区记录主引导表（MBR），记录以下分区
    - 主分区（Primary Partition）
    - 扩展分区（Extended Partition）
    - 逻辑分区（Logical Partition）
    ![](/.src/pic/imageS.png)
  - <codepub>[GPT分区](https://zh.wikipedia.org/zh-hant/GUID%E7%A3%81%E7%A2%9F%E5%88%86%E5%89%B2%E8%A1%A8)</codepub>：
    - 对于扇区为512字节的磁盘，MBR不支持大于2.2TB的存储器，为了支持更大的空间，厂商直接构建了4K扇区，以64bit为寻址基础的GPT使得最大容量约为37.4ZB
    - 与MBR类似，GPT分区表储存在GPT头，为了兼容MBR，也保留了MBR分区表的扇区，外观依然为MBR，但内部GPT分区使得拥有多于4个分区的数量扩充
    - 分区表中通过建立GUID识别分区

ext2文件系统
![](/.src/pic/imageT.png)
- 磁盘阵列：RAID
- 虚拟卷管理器：LVM
- 虚拟文件系统：VFS
## 文件共享
- 硬链接：就在另外的目录或本目录中增加目标文件的一个目录项，这样，一个文件就登记在多个目录中（不能对目录进行硬链接、不能在不同文件系统之间做硬链接）
- 软连接（符号链接、快捷方式）：
  - 符号链接文件是一种特别类型的文件，其中包含被链接文件的绝对路径名
  - 符号链接确实是一个新文件，当然它具有不同的I节点号；而硬链接并没有建立新文件

## 读写管理/存取控制

文件的所有权
![](/.src/pic/imageR.png)
  - 基于此的文件保护即：对于不同身份、不同组的用户，规定了他们的存取权限
  
## 文件系统可靠性

坏块管理
  - 硬件方面：磁盘的一个扇区上记载坏块清单（或磁盘驱动芯片做中继管理）
  - 软件方面：需要用户和文件系统维护一个坏块文件清单

备份常用策略
  - 完全备份
  - 增量备份（按照增量只备份修改的内容）
  - 更新备份（从上次完全备份到现在更新的全部文件）

文件系统一致性检查
  - 文件系统维护两张表：使用表与空闲表，1和0表示
  - 对两张表进行和运算比对，以检查文件系统是否出错