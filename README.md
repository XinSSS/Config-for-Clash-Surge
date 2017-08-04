# Conf-for-Surge-Shadowrocket
Surge Shadowrocket conf

## **万条规则让你爽到爆**

> 安卓有的iOS怎么能没有? 

安卓SS客户端中的绕过局域网和大陆, 其中所用到的配置文件其实是ChinaIP白名单 + GFWList黑名单, 但是一方面iOS几乎很少有人导入过完整的gfwlist, 另一方面现在的SS端中, 一般用的都是GEOIP库来判断IP是不是属于中国.

但是GEOIP的库是没有[IPIP的库](https://github.com/17mon/china_ip_list)做得好的, 再加上本人参考了[R0uter/ss.conf-for-surge](https://github.com/R0uter/ss.conf-for-surge) 和 [lhie1/Surge](https://github.com/lhie1/Surge) 这两个repo之后, 便完成了这个**万条规则让你爽到爆**的基于 黑名单 + 白名单模式 的配置文件, 完成了我长久以来的......



------



### 使用之前你需要更改哪些文件:


一般情况下, 仅需要修改`template`目录下的文件即可

使用Surge的情况的下,这里需要你去修改` surge_gfwlist&whiteIP_conf `这个文件, 在这里配置你的Proxy和ProxyGroup.

#### 请注意 !!! 

Surge的配置文件中,苹果服务器相关的ProxyGroup是`🍎PROXY`, 此组默认是direct直连. 
其他直连规则的ProxyGroup是`nProxy`, 默认也是direct直连. 
因此在配置你自己的服务器时, 请注意这两组和`Proxy`组, 不要删除, 因为已经和规则关联. 



***使用ShadowRocket的情况的下, 则可以不需要修改任何文件***

> 由于已经导入了比较全面的CN IP白名单 + GFWList黑名单, 所以你最后可以根据自己的情况去设置FINAL规则究竟是PROXY还是DIRECT, 就是说, 当你访问没有被墙的国外域名时, 你是想直连呢还是想走代理?

------



### 如何生成配置文件:

```python
#在此过程中, 你可能需要用到 pip install ....
python3 ssconf.py
```

等待命令执行完即可, 至此大功告成, configFileHere目录中将会生成相应客户端对应的配置文件



> PS: 
>
> 1. 由于引用的大部分规则是[gfwlist](https://github.com/gfwlist/gfwlist)和[china_ip_list](https://github.com/17mon/china_ip_list) , 所以在以后的过程中使用有问题的话, 除非是template中的模板文件, 否则还请大家多多提交pull request至这两个repo, 以维护我们爱国圈的健康成长
> 2. 为什么没有加广告过滤: 广告过滤规则大多比较繁琐并且有时效性, 也不怎么稳定, 所以我是不加REJECT规则的, 实在想要的话, 可以去参考[ss.conf-for-surge](https://github.com/R0uter/ss.conf-for-surge)这个项目的代码修改下即可
> 3. 不想要gfwlist怎么办?  参考代码中方法`genShadowrocketGFWAndChinaIPConf()`和`genSurgeGFWAndChinaIPConf()` 中的注释部分, 按照提示修改即可. 但是五千多条的IP白名单却是不能不要的, 这种情况下FINAL也得需要设置为PROXY. 至于精简IP白名单的话, 有识之士可以去修改[china_ip_list](https://github.com/17mon/china_ip_list) 
> 4. steam用户请看template\surge_gfwlist&whiteIP_conf 的312-314行,  或者是 template\shadowrocket_gfwlist&whiteIP_conf的287-289行, 上steam爱不爱国取决于你们当前的网络环境
> 5. 一般的规则很多都在GEOIP里面了而已,看不见, 我只是用了套另外的CNIP判断方法而已, 一万条真的一点都不多啊 ~~~~~




