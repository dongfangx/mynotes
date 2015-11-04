### ios8横屏广告freeze

#### 问题描述
- 平台:cocosx
- 语言:c++
- ios8中,横屏广告freeze

#### 解决思路
- AppController.mm 中，删除

```
if ( [[UIDevice currentDevice].systemVersion floatValue] < 6.0)
{
    [window addSubview: _viewController.view];
}
else
{
    [window setRootViewController:_viewController];
}
```

添加 [window setRootViewController:_viewController];

- RootViewController.mm 中，添加

```
- (void)viewWillDisappear:(BOOL)animated
{
    [super viewWillDisappear:animated];
    cocos2d::Director::getInstance()->stopAnimation();
}

- (void)viewWillAppear:(BOOL)animated
{
    [super viewWillAppear:animated];
    cocos2d::Director::getInstance()->startAnimation();
}
```