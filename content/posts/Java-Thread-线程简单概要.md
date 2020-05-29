---
title: "Java Thread 线程简单概要"
date: 2020-05-28T23:29:39+08:00
draft: false
---

# Java中的线程模型
Java是以**同步/阻塞**的方式运行的，他会一行一行执行。

开启一个线程的时候，会增加一个独立的栈：
Jvm的栈空间中除了Main的栈之外会增加一个与之**互相没有关联的栈**。

## 开启线程的方法
`new Thread().start()`

* 使用Runnable接口,实现接口后传入Thread；
```
	new Thread(() -> {
            System.out.println(" MyThread is:" + Thread.currentThread().getName());
        }).start();
```
* 继承Thread类，实现方法，然后通过调用start开启线程；
```
static class MyThread extends Thread {
        @Override
        public void run() {
            System.out.println(" MyThread is:" + this.getName());
        }
    }
```

## 线程中共享哪些资源
新的线程执行的内容会在一个**新的栈**中运行，则只属于栈的局部变量是不可共享的，反之其他的都是共享的，比如堆中的对象。


其实除了局部变量外共享所有资源（对象、静态常量、静态方法·····等等除了局部变量外）。

