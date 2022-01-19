# Conf-for-Surge-Shadowrocket
Surge Shadowrocket Quantumult conf

使用[Subconvert](https://github.com/tindy2013/subconverter)生成各种很方便的配置文件, 具体使用请查看[Subconvert文档](https://github.com/tindy2013/subconverter/blob/master/README-cn.md), 这里仅提供配置文件参考

```ini
[custom]
enable_rule_generator=true
overwrite_original_rules=true
clash_rule_base=https://raw.githubusercontent.com/XinSSS/Conf-for-Surge-Shadowrocket/master/clash_base.yaml
;设置规则标志位
ruleset=Steam,rules/DivineEngine/Surge/Ruleset/Extra/Game/Steam.list
ruleset=Xbox,rules/DivineEngine/Surge/Ruleset/Extra/Game/Xbox.list
ruleset=OneDrive,rules/DivineEngine/Surge/Ruleset/Extra/Microsoft/OneDrive.list
ruleset=PayPal,rules/DivineEngine/Surge/Ruleset/Extra/PayPal.list
ruleset=Apple,rules/DivineEngine/Surge/Ruleset/Extra/Apple/Apple.list
ruleset=StreamingSE,rules/DivineEngine/Surge/Ruleset/StreamingMedia/StreamingSE.list
ruleset=Streaming,rules/DivineEngine/Surge/Ruleset/StreamingMedia/Streaming.list
ruleset=Telegram,https://raw.githubusercontent.com/XinSSS/Conf-for-Surge-Shadowrocket/master/Telegram.list
ruleset=Proxies,rules/DivineEngine/Surge/Ruleset/Global.list
ruleset=China,rules/DivineEngine/Surge/Ruleset/China.list
ruleset=DIRECT,rules/LocalAreaNetwork.list
ruleset=China,[]GEOIP,CN
ruleset=Final,[]MATCH
;设置规则标志位

;设置分组标志位
custom_proxy_group=Steam`select`[]China`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]DIRECT
custom_proxy_group=Xbox`select`[]China`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]DIRECT
custom_proxy_group=OneDrive`select`[]Proxies`[]China`[]HK`[]SG`[]JP`[]TW`[]DIRECT
custom_proxy_group=PayPal`select`[]China`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]DIRECT
custom_proxy_group=Apple`select`[]China`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]DIRECT
custom_proxy_group=StreamingSE`select`[]China`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]US`[]DIRECT
custom_proxy_group=Streaming`select`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]US
custom_proxy_group=Telegram`select`[]Proxies`[]HK`[]SG`[]JP`[]TW`[]US
custom_proxy_group=Proxies`select`[]HK`[]SG`[]JP`[]TW`[]US`.*`[]DIRECT
custom_proxy_group=China`select`[]DIRECT`?i:CN|China|回国|中国|江苏|北京|上海|广州|深圳|杭州|常州|徐州|青岛|宁波|镇江|back`[]Proxies
custom_proxy_group=Final`select`[]Proxies`[]China`[]DIRECT
custom_proxy_group=HK`select`港|HK
custom_proxy_group=SG`select`新加坡|狮城|新|SG
custom_proxy_group=TW`select`台|新北|彰化|TW
custom_proxy_group=JP`select`日((?!用).)+|东京|大阪|埼玉|JP
custom_proxy_group=US`select`美|洛杉矶|硅谷|达拉斯|费利蒙|凤凰城|芝加哥|圣何塞|西雅图|圣克拉拉|US
;custom_proxy_group=HK`fallback`港`http://www.gstatic.com/generate_204`300
;设置分组标志位
```
