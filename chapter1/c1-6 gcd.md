#GCD

## 概述
```
dispatch_async(dispatch_get_global_queue(0, 0), ^{
    //0
    // 处理耗时操作的代码块...
    //通知主线程刷新
    dispatch_async(dispatch_get_main_queue(), ^{
        //回调或者说是通知主线程刷新，
    });
});
```
##eg
```
for (int i = 0 ; i < 10; i++) {
    dispatch_async(dispatch_get_global_queue(0, 0), ^{
    // 处理耗时操作的代码块...
     UIImage *img = [self getImgeWith:[urlArr objectForIndex:i]];
    //通知主线程刷新
    dispatch_async(dispatch_get_main_queue(), ^{
        //回调或者说是通知主线程刷新，
          [myImgV[i] setImage:img];
    });    
});
```

##备注
1. dispatch_get_global_queue(0, 0)，指用了全局队列。(2 最高,0 默认,-2 最低)
2. 3个队列:global_queue，current_queue,以及main_queue.
3. 

##结构
```
#define DISPATCH_QUEUE_PRIORITY_HIGH     2
#define DISPATCH_QUEUE_PRIORITY_DEFAULT  0
#define DISPATCH_QUEUE_PRIORITY_LOW     (-2)
```

