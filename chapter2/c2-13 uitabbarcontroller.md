#UITabBarController

## create
```
#import "YYAppDelegate.h"

@implementation YYAppDelegate

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    //1.创建Window
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    self.window.backgroundColor = [UIColor whiteColor];

    UITabBarController *tb=[UITabBarController new];
    self.window.rootViewController=tb;

    //b.创建子控制器
    UIViewController *c1=[[UIViewController alloc]init];
    c1.view.backgroundColor=[UIColor grayColor];
    c1.view.backgroundColor=[UIColor greenColor];
    c1.tabBarItem.title=@"消息";
    c1.tabBarItem.image=[UIImage imageNamed:@"tab_recent_nor"];
    c1.tabBarItem.badgeValue=@"123";

    UIViewController *c2=[[UIViewController alloc]init];
    c2.view.backgroundColor=[UIColor brownColor];
    c2.tabBarItem.title=@"联系人";
    c2.tabBarItem.image=[UIImage imageNamed:@"tab_buddy_nor"];

    UIViewController *c3=[[UIViewController alloc]init];
    c3.tabBarItem.title=@"动态";
    c3.tabBarItem.image=[UIImage imageNamed:@"tab_qworld_nor"];

    UIViewController *c4=[[UIViewController alloc]init];
    c4.tabBarItem.title=@"设置";
    c4.tabBarItem.image=[UIImage imageNamed:@"tab_me_nor"];


    //c.1第一种方式
//    [tb addChildViewController:c1];
//    [tb addChildViewController:c2];

    //c.2第二种方式
    tb.viewControllers=@[c1,c2,c3,c4];

    [self.window makeKeyAndVisible];
    return YES;
}

@end
```
## 属性和方法
```
viewcontroller.tabBarItem
c1.tabBarItem.title=@"消息";
c1.tabBarItem.image=[UIImage imageNamed:@"tab_recent_nor"];
```
## 备注
1. UITabBar的高度为49
2. 多可以显示5个Tab



