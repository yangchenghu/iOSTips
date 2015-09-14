# iOSTips
日常遇到的iOS方面的小tips，分享给大家


_2015-09-14_

##友盟统计与RNCachingURLProtocol冲突

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
                                       



