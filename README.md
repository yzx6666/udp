# udp

udp 项目
gsc qweqweqwe
#UDP实现流媒体广播系统

+ 由于是一个广播系统，C/S之间的通讯采用无连接的udp组播，组播相对于广播更加灵活并且节省资源，故采用组播技术
    
+ 由于需要考虑到节目单频道，让用户可以提前了解到每一个频道的类型，所以在各音乐频道内容的基础上，加上节目单频道，这样无需遍历每一个频道，就可以知道各频道的内容，从而针对性的选择。因此需要规定节目单数据格式和节目频道数据格式
    
+ 由于广播的内容是音乐（后续可延伸扩展为视频），所以需要进行流量控制。流量控制采用令牌桶实现，可设置传输的速率。
    
+ 由于频道数目媒体库信息调整，故采用多线程获取并发送频道数据。不涉及多线程之间的通讯，需要考虑的令牌桶资源的互斥访问。
    
+ 服务器最后以守护进程方式运行，系统运行过程中的数据采用系统日志保存。
