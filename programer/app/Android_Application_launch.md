# Android Application Launch
[ActivityManagerService 源码](https://android.googlesource.com/platform/frameworks/base/+/4f868ed/services/core/java/com/android/server/am/ActivityManagerService.java)

## Android 不同的地方
据[文档描述](#)
1. 每个 Android app 都运行在自己的进程里面，并且有唯一的 user ID
2. Android app 都具有不同的 *部件* , 这些 *部件* 都能被其它的 App 唤醒，特别它们都没有统一的入口，如 main()  函数

### App 的 *部件* 有以下四类：
- Activities
- Services, 后台任务运行
- Broadcast Receivers，Intent 的接收器
- Content providers，数据保存共享

## Application Launch process

![](DraggedImage.png)

`startActivity()` 在 `ActivityManagerService` 会通过 Binder IPC 执行以下步骤启动 `Activity` 
1. 收集信息，intent 的 **目标对象**，这会由 `PackageManager` 的 `resolveIntent()` 完成,`PackageManager.MATCH_DEFAULT_ONLY` and `PackageManager.GET_SHARED_LIBRARY_FILES` flags 是默认设置
2. 目标对象信息存储好，防止再做同样动作
3. 检查是否有权限启动 *目标对象* ，用 `grantUriPermissionLocked ()`
4. 如果有权限，`ActivityManagerService` 会检查是否需要将 *目标 Activity* 启动在新的 task 里，这取决于 Intent 上的标记，譬如：`FLAG_ACTIVITY_NEW_TASK`, `FLAG_ACTIVITY_CLEAR_TOP` 等等
5. 检查 `ProcessRecord ` 是否存在 process 

## 进程启动的几个阶段
1. 进程的创造 (Process Creation)
2. 绑定 App (Binding Applicaiton)
3. Launching Activity / Starting Service 等等的步骤

## 推荐阅读资料：
下面这篇治疗，谈述编译和运行的，浅谈的
- [How Android Apps are Built and Run](https://github.com/dogriffiths/HeadFirstAndroid/wiki/How-Android-Apps-are-Built-and-Run)

运行的步骤简介，不错的文章
- [Android Application Launch](http://multi-core-dump.blogspot.jp/2010/04/android-application-launch.html)
- [Android Application Launch Part 2](http://multi-core-dump.blogspot.jp/2010/04/android-application-launch-part-2.html)

下面这篇文章的调查也很不错，写了 Zygote 和一些运行的底层
- [Processes and the Zygote](http://coltf.blogspot.jp/p/android-os-processes-and-zygote.html)

