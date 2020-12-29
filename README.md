# 函数调用原理



这是一篇讲述函数调用原理的文章，通过大量的示意图从比较基础的概念开始阐述函数调用时堆栈的完整变化过程，同时还会通过一个具体例子来分析在X-64平台上函数的调用过程，从而理解函数调用原理。最后会提供几个例子来发现C语言函数栈帧的一些有意思的行为。

文章提供了[gitbook](https://acodercat.github.io/function-call-principle/)的阅读方式。



## 目录

* [前置知识](https://acodercat.github.io/content/function-call-principle/pre-knowledge.html)
* [内存中的栈](https://acodercat.github.io/content/function-call-principle/stack-in-memory.html)
* [控制转移](https://acodercat.github.io/content/function-call-principle/control-transfer.html)
* [数据传递](https://acodercat.github.io/content/function-call-principle/data-transfer.html)
* [寄存器的保存与恢复](https://acodercat.github.io/content/function-call-principle/save-and-restore-of-registers.html)
* [局部变量的存储](https://acodercat.github.io/content/function-call-principle/storage-of-local-variables.html)
* [函数栈帧](https://acodercat.github.io/content/function-call-principle/function-stack-frame.html)
* [C语言函数栈帧实例](https://acodercat.github.io/content/function-call-principle/c-stack-frame-example.html)
* [一个有趣的例子](https://acodercat.github.io/content/function-call-principle/interesting-example.html)
* [手动修改栈帧数据](https://acodercat.github.io/content/function-call-principle/modify-stack-frame-data.html)
* [总结](https://acodercat.github.io/content/function-call-principle/summary.html)



## 本文可以收获什么？

* 函数间如何转移控制
* 函数间如何传递数据
* 栈帧的初始化与销毁
* C/C++数组越界的危害
* 为什么内联（inline）函数效率高
* 为什么尽量用循环来代替递归调用
* 为什么静态变量在函数返回后不会被释放
* 什么是栈溢出攻击



## 其他

文中有一个重要的概念`内存对齐`没有提及，由于它不属于函数调用范畴之内，也就没有对它进行说明。我在构造示例时也避免了编译器为了内存对齐而出现一些额外指令，所以文中也见不到它的影子。如果你有兴趣可以通过网络去了解与它相关的内容。



## 相关资源

* 书籍：

  《深入理解计算机系统》（第三版）

  《汇编语言》（王爽第三版）

* 公开课：

  《编程范式》（斯坦福公开课）

  

## 绘图工具

文中所有图片都使用了[excalidraw](https://excalidraw.com/)作为绘图工具，这是一款非常棒的在线绘图工具，它提供了不同风格的绘制模式。