# 虚拟存储管理
起因：进程在执行之前要全部装入内存，这种限制是不合理的。最理想的状态是按需调入程序

按需分别调入内存会带来两点好处：
  - 用户编制程序时不必考虑内存容量的限制
  - 在一定容量的内存中就可同时装入更多的进程

虚拟存储管理：用户能作为可编址内存对待的虚拟存储空间，它使用户逻辑存储器与物理存储器分离，是操作系统给用户提供的一个比真实内存空间大得多的地址空间

虚拟存储器的特征
- 虚拟扩充
- 部分装入
- 离散分配
- 多次对换