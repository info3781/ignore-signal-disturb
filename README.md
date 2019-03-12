问题：最近在做`iOS UI`卡顿监控，为了具体定位到卡顿的函数栈，使用到了`pthread_kill`，但是`debug`状态下，`gdb`会被`signal`干扰

下面是两种解决方案，第二种其实也是第一种的扩展

* `process handle -s0 -n0 -p1 SIGUSR1`
> [pthread_kill in IOS causes debugger to stop app.](https://forums.developer.apple.com/thread/105415#319675)

* 通过设置`symbolic breakpoint`来执行上述`"process handle" command`
具体配置如下:
![symbolic breakpoint image](https://upload-images.jianshu.io/upload_images/671666-f799d523a7d62ff2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

