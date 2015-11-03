#内存管理

## Block
```
int result = ^(int a){return a*a;}(5);  
NSLog(@"%d", result);
```

## Block Pointer
```
//声明一个square的Block Pointer，其所指向的Block有一个int输入和int输出  
__block int num = 8;            //__weak
int (^square)(int);  
//将Block实体指定给square  
square = ^(int a){ 
    num = 5;
    return a*num ; 
};  
//调用方法，感觉是是不是很像function的用法？  
NSLog(@"%d", square(5));

/*
把Block Pointer当成参数传递给一个function
*/
void myFunction(int (^mySquare)(int));     //function的定义，将Block作为参数  
int (^mySquare)(int) = ^(int a){return a*a;};   //定义一个mySquare的Block pointer变量  
myFunction(mySquare);    //把mySquare作为myFunction的参数 

//上面的三行代码其实等价于下面这行代码：
myFunction( ^int(int a){return a*a;} ); 

//作为参数
- (void)objcMethod:(int(^)(int))square;
```
## Block回调
```
//1.定义
typedef void (^UpdateAlertBlock)();  
@property (nonatomic, copy) UpdateAlertBlock updateAlertBlock;

//2.使用1
timer.updateAlertBlock = ^()  
{  
    UIAlertView *alert=[[UIAlertView alloc] initWithTitle:@"提示" message:@"时间到" delegate:self cancelButtonTitle:nil otherButtonTitles:@"确定",nil];        
    alert.alertViewStyle=UIAlertViewStyleDefault;  
    [alert show];  
};

//3.使用2    
if (self.updateAlertBlock)  
{  
    self.updateAlertBlock();  
}
```
## eg
[1. Block函数回调](http://www.tuicool.com/articles/JFRfmq)

