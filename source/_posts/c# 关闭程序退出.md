---
categories: 
- 编程开发
tags:
- C#
---
#### c# 关闭程序退出

**this.Close();**   //只是关闭当前窗口，若不是主窗体的话，是无法退出程序的，另外若有托管线程（非主线程），也无法干净地退出；  

**Application.Exit();**  //强制所有消息中止，退出所有的窗体，但是若有托管线程（非主线程），也无法干净地退出；  

**Application.ExitThread();** //强制中止调用线程上的所有消息，同样面临其它线程无法正确退出的问题；  

**System.Environment.Exit(0);**   //这是最彻底的退出方式，不管什么线程都被强制退出，把程序结束的很干净，退出时有可能会抛出异常  

**System.Diagnostics.Process tt = System.Diagnostics.Process.GetProcessById(System.Diagnostics.Process.GetCurrentProcess().Id);**
**tt.Kill();**//直接杀死与本程序相关的所有进程，有可能会导致数据丢失，但是不会抛出异常。  