---
title: Notification Q&A
date: 2014-11-24
categories: Android
---
>昨天(2014-11-23)第一次接触了安卓中的Notification，在实现Demo遇到了一些小问题。这里把其中一些记录下来，以供后人(我自己)参考


### Q1：Notification为何物？

Notification，从字面意思而言，就是通知。通知会一直停留在通知栏中，并且按照优先级和时间排序。就比如别人在QQ中发给你一条消息，那么就会在通知栏中得到体现。  
Notification还有一些额外功能，比如震动和提示音，或者持续提醒。

### Q2：如何创建最基本的Notification？

如何发出Notification呢，首先构造一个Notification
```Java
Notification.Builder builder = new Notification.Builder(MyActivity.this);
builder.setSmallIcon(R.drawable.ic_launcher);
Notification notification = builder.build();
```
这里用Notification.Builer构造Notification，其中setSmallIcon是必要的，如果没有调用该函数，Notification不会出现。  
构造完Notification后，使用NotificationManager激活Notification
```Java
NotificationManager notificationManager = (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);
notification.notify("tag", id, notification);
```
相同的tag和相同的id，会使notification被替换，要注意

### Q3：如何设置Notification的内容？

你可以在Notification中加入文字、替换图标，甚至是使用自定义的View。这里只讲标题和图标  
- `setContentTitle()`设置标题
- `setContentText()`设置文字
- `setLargeIcon()`会使小图标显示在右下角，并改变左边的大图标图标
- `setContentInfo`在小图标旁边的文字
- `setNumber`在小图标旁边的数字

使用这些方法，就能改变Notification的内容。

### Q4：怎么让Notification“BIU”的一下跳出来？

这里提供一些方法，让你的Notification引人注目。
- `setTicker()`激活时，会占满整个通知栏
- `setVibrate()`激活时震动
- `setSound()`激活时播放声音
- `setLight()`激活时闪光
后面三个方法可以用`setDefaults()`来简单实现

### Q5：怎么让通知栏中的Notification一点就消失？

通常情况下，Notification需要NotificationManager的cancel()方法进行消除。  
如果需要让他一点就消失，需要为Notification设置autoCancel。  
autoCancel设置完之后，仍需要setContentIntent，autoCancel才会生效。
