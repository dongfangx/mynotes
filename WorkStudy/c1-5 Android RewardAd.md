### Android RewardAd

#### 问题描述
- 平台:cocosx
- 语言:c++
- 问题1:视频广告播放完后，会Activity切换，调用applicationWillEnterForeground，弹出全屏广告
- 问题2:在可以关闭的视频广告播放时resume游戏，游戏一直卡在loading界面

#### 问题1-解决思路
- 在播放视频广告后，添加全局变量，标记是视频广告播放，
- 在applicationWillEnterForeground 中，根据标记，跳过全屏广告

#### 问题2-解决思路
- 设置AndroidManifest.xml 中 android:launchMode="singleTop"