#UINavigationController

## create
```
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    self.window.backgroundColor = [UIColor whiteColor]; 

    LoginFirstVc *vc = [LoginFirstVc new];
    UINavigationController *navVc = [[UINavigationController alloc] initWithRootViewController:vc];
    self.window.rootViewController = navVc;
    navVc.navigationBar.hidden = YES;
    [self.window makeKeyAndVisible];
}

- (void)viewDidLoad  
{  
    [super viewDidLoad];  

    UIBarButtonItem *leftButton = [[UIBarButtonItem alloc] initWithBarButtonSystemItem:UIBarButtonSystemItemAction target:self action:@selector(selectLeftAction:)];  
    self.navigationItem.leftBarButtonItem = leftButton;  

    UIBarButtonItem *rightButton = [[UIBarButtonItem alloc] initWithBarButtonSystemItem:UIBarButtonSystemItemAdd  target:self action:@selector(selectRightAction:)];  
    self.navigationItem.rightBarButtonItem = rightButton;
}```
## 值
```
```
## 属性
```
pushViewcontroller
popViewController
```
## 其他扩展

