# <img src="../../images/icon/java.png" width="30" height="23" />线程

---

**JAVA线程的一些整理**

<img src="../../images/icon/java.png" width="180" height="140" />

## 可见性

**线程之间的共享变量值的修改后的同步策略为，在某一线程中更新过的共享变量需要刷新到主内存中，主内存将最新的变量值更**
**新到其他线程的工作内存中，如果其中任一环节出现问题，就会造成线程中出现的数据问题，也就是多线程中线程不安全问题，要**
**实现共享变量的可见性，必须保证线程修改后的共享变量及时从工作内存中刷新到主内中，其他线程能够及时把共享变量的最新值从**
**主内存中更新到自己的工作内存中**

* **可见性：一个线程对共享变量值的修改，能够及时的被其他线程看到**

* **共享变量：如果一个变量在多个线程的工作内存中都存在副本，那么这个变量就是这几个线程额共享变量**

* **所有的变量都存储在主内存中**

* **每个线程都有自己独立的工作内存，里面保存改线程使用到的变量副本（主内存中改变量的一份拷贝）**

* **线程对共享变量的所有操作都必须在自己的工作内存中进行，不能直接从主内存中读写**

* **不同的线程之间无法直接访问其他线程工作内存中的变量，线程间变量的值传递需要通过主内存来完成**