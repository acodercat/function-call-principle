> 本文通过的大量示意图从比较基础的概念开始阐述函数执行时堆栈的完整变化过程，最后通过一些具体例子来分析在X-64平台上函数的调用过程，从而理解函数调用原理。文章放在了[gitbook](https://acodercat.github.io/function-call-principle/)以供阅读。



## 目录

* [前置知识](https://acodercat.github.io/function-call-principle/pre-knowledge.html)
* [控制转移](https://acodercat.github.io/function-call-principle/control-transfer.html)
* [数据传递](https://acodercat.github.io/function-call-principle/data-transfer.html)
* [寄存器的保存与恢复](https://acodercat.github.io/function-call-principle/save-and-restore-of-registers.html)
* [局部变量的存储](https://acodercat.github.io/function-call-principle/storage-of-local-variables.html)
* [函数栈帧](https://acodercat.github.io/function-call-principle/function-stack-frame.html)
* [C语言函数栈帧实例](https://acodercat.github.io/function-call-principle/c-stack-frame-example.html)
* [一个有趣的例子](https://acodercat.github.io/function-call-principle/interesting-example.html)
* [栈溢出攻击](https://acodercat.github.io/function-call-principle/stack-overflow-attack.html)



## 相关资源

* 书籍：

  《深入理解计算机系统》

  《汇编语言》（王爽第三版）

* 公开课：

  《编程范式》（斯坦福公开课）

  

## 绘图工具

文中所有图片都使用了[excalidraw](https://excalidraw.com/)作为绘图工具，这是一款非常棒的在线绘图工具，它提供了不同风格的绘制模式。