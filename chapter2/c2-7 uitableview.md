#UITableView

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIView *headerView = [[[UIView alloc] init] autorelease];
    headerView.frame = CGRectMake(0, 0, 710, 70);                       
    headerView.backgroundColor = [UIColor clearColor];

    UITableView *homeTableView = [[[UITableView alloc] init] autorelease];

    homeTableView.frame =CGRectMake(0, 0, 620, 585);    
    homeTableView.delegate=self;
    homeTableView.dataSource =self;
    homeTableView.transform =CGAffineTransformMakeRotation(-M_PI /2); //tableview逆时针旋转90度
    homeTableView.center = CGPointMake(730, 425);                                 

    homeTableView.showsVerticalScrollIndicator = NO;
    homeTableView.backgroundColor = [UIColor clearColor];
    homeTableView.allowsSelection = NO;
    homeTableView.separatorStyle = UITableViewCellSeparatorStyleNone;
    [self.view addSubview:homeTableView];
    homeTableView.tableHeaderView = headerView;
}

#pragma mark -UITableView

- (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section
{    
    return ([self.componentArray count] + 1) / 2;
}

- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath
{
    return 108.0;
}

- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
{
    int index = indexPath.row * 2;    
    HomeCell *cell =[tableView dequeueReusableCellWithIdentifier:@"identifier"];
    if (cell == nil) {
        cell =[[[HomeCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:@"identifier"] autorelease];
        cell.transform =CGAffineTransformMakeRotation(M_PI /2);
        cell.delegate = self;        
    }    
    [cell loadView:isHidden rowTag:kCELL_ROW1_TAG index:index isSel:isSel com:com1]
    return cell;
}
```
## 值
```
typedef enum {
    UITableViewCellSeparatorStyleNone,
    UITableViewCellSeparatorStyleSingleLine,
    UITableViewCellSeparatorStyleSingleLineEtched
} UITableViewCellSeparatorStyle;
```
## 属性
```
```
## 其他扩展
## 详细见文档

