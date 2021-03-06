# 死锁
<codepub>死锁</codepub>：两个或两个以上的进程在执行过程中，由于竞争资源或者由于彼此通信而造成的一种阻塞的现象，若无外力作用，它们都将无法推进下去

产生死锁的根本原因是**资源有限且操作不当**

产生死锁的必要条件
  1. <codepub>互斥</codepub>
  3. <codepub>不可抢占</codepub>
  2. <codepub>占有且等待</codepub>
  4. <codepub>循环等待</codepub>
  - 只要有一个必要条件不满足，则死锁就可以排除。

## 饥饿
饥饿：所有的程序都在不停地运行，但都等待不到自己所需的资源，进而无法取得进展

饿死与死锁的关系
- 相同点：二者都是由于竞争资源而引起的
- 不同点：
  1. 死锁都处于等待状态（blocked），非等待状态可能被饿死
  1. 死锁在等待永远不会被释放的资源，饿死在等待会被释放但分不到给自己的资源，表现为持续等待
  1. 死锁一定发生了循环等待，饿死则不一定。所以死锁可以检测，饿死难以检测
  1. 死锁一定涉及多个进程，饿死可以有单个或多个
  1. 死锁会使整个系统崩溃，饿死能保证系统内有一个进程能正常运行，只是饥饿进程得不到机会

## 预防死锁
- **破坏占有且等待条件**：不占有资源时才可以申请资源
- **破坏“请求和保持”条件**：使用资源逐步分配的方法，如银行家算法
- **破坏“不可抢占”条件**：资源可以被有条件争夺
- **破坏“循环等待”条件**：[哲学家就餐问题](#进程调度经典问题)中的资源分级思路（依序分配）、或先弃大后取小（一个进程申请资源，必须放弃多于索取的资源）

## 避免死锁
  - 安全状态：
    - 目的：为系统设计一个安全状态，每次分配资源时候对齐进行检查和调整并作出相应工作，属于监控作用
    - 描述：**若对于每一个进程，它需要的附加资源可被系统中当前可用资源与所有进程当前占有资源之和所满足，则为一个安全状态序列**。
  - [银行家算法](https://zh.wikipedia.org/wiki/%E9%93%B6%E8%A1%8C%E5%AE%B6%E7%AE%97%E6%B3%95)：在銀行中，客戶申請貸款的數量是有限的，每個客戶在第一次申請貸款時要聲明完成該專案所需的最大資金量，在滿足所有貸款要求時，客戶應及時歸還。銀行家在客戶申請的貸款數量不超過自己擁有的最大值時，都應儘量滿足客戶的需要。在這樣的描述中，銀行家就好比作業系統，資金就是資源，客戶就相當於要申請資源的行程。

[关于死锁、活锁和饥饿](https://www.jianshu.com/p/0494ab7c96f9)：活锁可以认为是一种特殊的饥饿（过度谦让）