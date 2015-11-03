#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIWebView *webView = [UIWebView new];
    webView.frame = [[UIScreen manScreen]applicationFrame];
    NSURLRequest *request = [NSURLRequest requestWithURL:[NSURL URLWithString:@"http://www.dbw.cn"]]; 
    [webView loadRequest:request];
    webView.delegate = self;
    webView.scalespageToFit = YES;
    webView.detectsPhoneNumbers = YES;
    [self.view addSubview:webView];

    //[webView goBack];  
    //[webView goForward];  
    //[webView reload];//重载  
    //[webView stopLoading];//取消载入内容 
}

- (void )webViewDidStartLoad:(UIWebView*)webView   //网页开始加载的时候调用
{    
}
- (void )webViewDidFinishLoad:(UIWebView*)webView  //网页加载完成的时候调用
{    
}
- (void)webView:(UIWebView*)webView didFailLoadWithError:(NSError *)error //网页加载错误的时候调用
{    
}
```
## 值
```
```
## 属性
```
```
## 其他扩展
## 详细见文档

