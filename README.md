# iOSTips
日常遇到的iOS方面的小tips，分享给大家


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
                                       



