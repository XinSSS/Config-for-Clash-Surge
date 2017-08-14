# Conf-for-Surge-Shadowrocket
Surge Shadowrocket Quantumult conf

## **万条规则让你爽到爆**

> 安卓有的iOS怎么能没有? 

安卓SS客户端中的绕过局域网和大陆, 其中所用到的配置文件其实是ChinaIP白名单 + GFWList黑名单, 但是一方面iOS几乎很少有人导入过完整的gfwlist, 另一方面现在的SS端中, 一般用的都是GEOIP库来判断IP是不是属于中国.

但是GEOIP的库是没有[IPIP的库](https://github.com/17mon/china_ip_list)做得好的, 再加上本人参考了[R0uter/ss.conf-for-surge](https://github.com/R0uter/ss.conf-for-surge) 和 [lhie1/Surge](https://github.com/lhie1/Surge) 这两个repo之后, 便完成了这个**万条规则让你爽到爆**的基于 黑名单 + 白名单模式 的配置文件, 完成了我长久以来的......



------



### 使用之前你需要更改哪些文件:

##### 使用ShadowRocket的情况的下, 则可以不需要修改任何文件直接导入即可使用
---

使用Surge的情况的下, 需要在 `surge_gfwlist&whiteIP.conf` 添加你的Proxy和配置ProxyGroup.

##### 请注意 !!! 修改Surge的ProxyGroup时, 请仔细阅读注释, 勿删除(可修改)已经和规则相关联的ProxyGroup: `🍎PROXY` `Proxy` `nProxy` `FinalProxy` , 解释下同Quantumult

##### 使用Quantumult的情况的下, 请在Favorite中添加TCP FILTER, Replace后请注意, `🍎PROXY` 为苹果服务器的连接规则, `Proxy`为一般情况下的代理规则, `nProxy`为直连规则, `FinalProxy` 则请看如下提示.

> 由于已经导入了比较全面的CN IP白名单 + GFWList黑名单, 所以你最后可以根据自己的情况去设置FINAL规则究竟是PROXY还是DIRECT, 就是说, 当你访问没有被墙的国外域名时, 你是想直连呢还是想走代理?

------



### 如何使用&更新&生成配置文件:

你可以直接复制配置文件URL:

Surge: https://raw.githubusercontent.com/XinSSS/Conf-for-Surge-Shadowrocket/master/configFileHere/surge_gfwlist%26whiteIP.conf

Shadowrocket: https://raw.githubusercontent.com/XinSSS/Conf-for-Surge-Shadowrocket/master/configFileHere/shadowrocket_gfwlist%26whiteIP.conf

Quantumult: https://raw.githubusercontent.com/XinSSS/Conf-for-Surge-Shadowrocket/master/configFileHere/quan_gfwlist%26whiteIP.conf

也可以自行通过python脚本自动根据GFWList和china_ip_list的github生成最新的配置文件, **Surge请注意**:生成文件之前可以先行修改`template`目录中的`surge_gfwlist&whiteIP_conf`配置你的服务器.

```python
#在此过程中, 你可能需要用到 pip install ....
python3 ssconf.py
```

等待命令执行完即可, 至此大功告成, configFileHere目录中将会生成相应客户端对应的配置文件



> PS: 
>
> 1. 由于引用的大部分规则是[gfwlist](https://github.com/gfwlist/gfwlist)和[china_ip_list](https://github.com/17mon/china_ip_list) , 所以在以后的过程中使用有问题的话, 除非是template中的模板文件, 否则还请大家多多提交pull request至这两个repo, 以维护我们爱国圈的健康成长
> 2. 为什么没有加广告过滤: 广告过滤规则大多比较繁琐并且有时效性, 也不怎么稳定, 所以我是不加REJECT规则的, 实在想要的话, 可以去参考[ss.conf-for-surge](https://github.com/R0uter/ss.conf-for-surge)这个项目的代码修改下即可
> 3. 不想要gfwlist怎么办?  参考代码中方法`genXXXXXX()` 中的注释部分, 按照提示修改即可. 但是五千多条的IP白名单却是不能不要的, 这种情况下FINAL也得需要设置为PROXY. 至于精简IP白名单的话, 有识之士可以去修改[china_ip_list](https://github.com/17mon/china_ip_list) 
> 4. 一般的规则很多都在GEOIP里面了而已,看不见, 我只是用了套另外的CNIP判断方法而已, 一万条真的一点都不多啊 ~~~~~




