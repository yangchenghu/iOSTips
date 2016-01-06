# iOSTips
日常遇到的iOS方面的小tips，分享给大家


_2016-01-07_

## UITableView 顶部空白的处理方法

解决方式1：
self.tableView.tableHeaderView = [[UIView alloc] initWithFrame:CGRectMake(0.0f, 0.0f, self.tableView.bounds.size.width, 0.01f)];
 
解决方式2：
self.tableView.contentInset = UIEdgeInsetsMake(-30 , 0 , 0 , 0);
 
解决方式3：
self.automaticallyAdjustsScrollViewInsets = NO;

## NavigationController 添加滑动返回上一级功能

	self.navigationController.interactivePopGestureRecognizer.enabled = YES;
    self.navigationController.interactivePopGestureRecognizer.delegate = nil;


_2015-10-25_

## UITableView被上层的NavigationBar遮挡

界面编辑器创建navigationController，可以通过Simulated Metrics，将Top Bar设置为Opaque Navigation Bar即可



## NavigationBar上的返回按钮显示“返回”

需要在上一级页面的ViewDidLoad方法中加入以下语句

	    self.navigationItem.backBarButtonItem = [[UIBarButtonItem alloc] initWithTitle:@"返回" style:UIBarButtonItemStylePlain target:nil action:nil];






_2015-09-14_

## 友盟统计与RNCachingURLProtocol冲突

今天发现友盟的统计没有了，注释了好多代码才发现跟这个`RNCachingURLProtocol `框架有关系

原因

	由于RNCachingURLProtocol，把SDK发的post请求转为get请求，导致出现这样的报错


[处理方法](http://bbs.umeng.com/thread-4029-1-1.html)


_2015-09-11_

## 监听音量键事件


添加监听事件

	[[UIApplication sharedApplication] beginReceivingRemoteControlEvents];
        
    [[NSNotificationCenter defaultCenter] addObserver:self
                                             selector:@selector(volumeChanged:)
                                                 name:@"AVSystemController_SystemVolumeDidChangeNotification"
                                               object:nil];
                                                   
移除监听事件

	[[NSNotificationCenter defaultCenter] removeObserver:self name:@"AVSystemController_SystemVolumeDidChangeNotification" object:nil];
    
    [[UIApplication sharedApplication] endReceivingRemoteControlEvents];
    
----    
                                       



