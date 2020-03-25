此页面最近一次更新时间：2020.03.24                 
[返回到首页](https://passwallopenwrt.github.io/website/)            

【passwall复杂度较高，高阶用法可以实现你能想到的很多需求，需要看教程和多摸索，没空学习教程或者水平不够搭配出错的请不要使用高阶用法，默认的设置已经能够满足99%人群了，使用默认设置或者不用都可以】       

* 手动更新passwall按钮，使用的话，只会更新passwall这个luci包而已，而passwall只是个方便小白使用的提供UI的控制器而已，底层调用的trojan v2ray ip2socks等等真正在运行的客户端二进制程序文件并不会更新，所以你无法使用更新版本的优化的上游trojan v2ray等实际客户端，虽然你可以用最新的passwall搭配旧的底层二进制程序文件，一样能用，但终归体验不能保证是最优的，也不能保证一直可以新passwall搭配旧二进制程序文件没问题，所以还是刷入（[不保留配置](./upgrade.md)刷入可避免兼容性风险）最新源码编译的完整固件为最优选择。并且，openwrt其他的多如牛毛的组件的更新，你也不更了？其他的插件的bug修复和优化也不要了？         
* 有些主题兼容性不好，在使用个别的luci插件时会出不显示错显示等bug,不想遇到这些问题请使用默认的主题(bootstrap类主题)                    
* “旁路由”模式下，无法访问国内网络，在防火墙自定义规则添加：           
iptables -t nat -I POSTROUTING -j MASQUERADE                 
* 默认未设置允许的设备不能使用代理、自由指定不同客户端使用不同线路（盒子看Netflix）：[教程](https://youtu.be/qkga9DN5H08)       
* passwall的负载均衡：[教程](https://youtu.be/TRdOfTykgRw)                 
* 开源项目，没有团队负责内测，每次提交完代码都是大家公测。你能正常用老版本就没必要追更新！
* 不保留配置升级：[图文](./upgrade.md)                 
* 请务必保持启用passwall的高级设置里的守护进程！      
* 在passwall插件运行中状态下，如果修改LAN口的静态IP，可能会导致无法上网。重启passwall插件或者重启固件即可解决！          
* 如果出现YouTube等一些网站的页面上的特定内容错误显示，比如广告区域加载失败，只有框框没有图片，大概率是你的系统（不是固件！）的负责域名快速解析的HOSTS文件在作妖，解决办法是删除HOSTS文件里的所有规则（# 号注释掉的内容可以不管，其他的都删掉）    
* 始终无法连接到软路由网络、始终无网络：[可能解决办法](./winproxy.md)               
* 测速：[注意事项](./speed.md)        
* ipv6：[注意事项](./ipv6.md)                
* 多线多拨：如果失败，尝试“使用旧的macvlan创建方式”勾选或不勾选            
* WIFI信号觉得不好？：首先请关闭使用5G优选（智能选频），然后2.4G信号锁死在20MHz，5G信号锁死在你的手机等设备支持到的最高的即可（最近160MHz的也都开始普及了...），这样你离天线远时手动连2.4G信号，离得近时手动连5G信号                  
* 基于Chromium内核的浏览器建议关闭QUIC：[教程](https://www.echoteen.com/turnoff-quic.html)               
* 修改win10的tcp配置参数来提升打开youtube的速度：[教程](https://bincode.cc/ssr-win10-tcp-youtube-speed/)                    
* 如何DDNS外网无需加端口远程访问 dynuDNS解析 URL转发 治愈强迫症：[教程](https://youtu.be/c4HSZzTM7G0)             
* 单线or双线，最简单的iptv内网融合教程，需要懂一点基础：[教程](https://github.com/luckyyyyy/blog/issues/44)         
* 小提示：使用负载均衡同样可以实现故障切换的功能          
* passwall的恢复默认配置方法：地址栏输入例：                      
  http://192.168.1.1/cgi-bin/luci/admin/vpn/passwall/reset_config        
  passwall的隐藏菜单方法：地址栏输入例：                 
  http://192.168.1.1/cgi-bin/luci/admin/vpn/passwall/hide                            
  当你隐藏后想再次显示，地址栏输入例：                  
  http://192.168.1.1/cgi-bin/luci/admin/vpn/passwall/show                 
  
     

