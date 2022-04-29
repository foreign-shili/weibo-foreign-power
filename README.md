# 微博境外势力

使用您的规则代理工具，在微博上成为境外势力。

> 此项目目前支持：
 * [Clash for Windows](#ClashForWindows)
 * [Quantumult X、Shadowrocket、Surge](#Surge)
 * [v2ray 系、SagerNet、Matsuri](#v2ray)
 * 欢迎 Pull Request 添加更多规则工具
 
---

## 前情提要

[IP属地功能升级公告 — @微博管理员](https://weibo.com/1934183965/LqvYeCdBu) （[文字版本](./misc/IP%E5%B1%9E%E5%9C%B0%E5%8A%9F%E8%83%BD%E5%8D%87%E7%BA%A7%E5%85%AC%E5%91%8A.md)）

---

### <a id="ClashForWindows"> Clash for Windows </a>

请确保您的 Clash For Windows 版本高于 0.11.10。可到 [Clash for Windows 发布页面](https://github.com/Fndroid/clash_for_windows_pkg/releases) 更新。

前往 `Settings → Profiles`，点击 Parsers 的 Edit 按钮。

![](https://i.ibb.co/mytXpCZ/image.png)

在文本编辑器中，覆盖为以下内容 **（您需要将下方的「代理」文本替换成您配置文件的代理选项，如：`🚀 节点选择`、`🇭🇰 香港节点` 等）**：

```yaml
parsers:
  - reg: ^.*$ # 或使用 - url: https://example.com/profile.yaml 指定订阅
    yaml:
      prepend-rules: # 规则由上往下遍历，如上面规则已经命中，则不再往下处理
        - DOMAIN-SUFFIX,weibo.com,代理
        - DOMAIN-SUFFIX,weibo.cn,代理
        - DOMAIN-SUFFIX,weico.cc,代理 # Weico 客户端
```

包括 `IP-CIDR` 的规则在此：[weibo_clash.yaml](./modules/weibo_clash.yaml)

保存并关闭您的文本编辑器。然后在 Profiles 中，重新刷新您的订阅。规则会自动应用到更新后的订阅。

如果您正在使用其它的配置 Parser，您也可以将以上三个规则添加到 `prepend-rules` 的最顶端。
<!-- ### <a id="QuantumultX"> -->

### <a id="Surge"> Quantumult X/Surge/Shadowrocket </a>

在 Quantumult X、Shadowrocket 或 Surge 客户端中，导入并启用以下模块。

`https://raw.githubusercontent.com/foreign-shili/weibo-foreign-power/main/modules/weibo_weibo_quanx_srocket_surge.conf`

或是手动创建新模块，拷贝以下文件的内容，然后粘贴到新模块中：

[weibo_quanx_srocket_surge.conf](./modules/weibo_quanx_srocket_surge.conf)

### <a id="v2ray"> v2ray 系、SagerNet、Matsuri </a>

请确保您的客户端拥有最新的 v2ray 路由规则（`geoip.dat`、`geosite.dat`）。推荐从 [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 更新您的路由规则数据库。

#### 懒人方式：

在相关客户端的规则设定中，将 `geosite:sina` 放置在需要代理规则的最顶端。这样做是最简单的，但可能会导致 sinaimg.cn（目前访问不影响地域显示）等图片、视频资源通过代理加载，造成流量浪费、加载缓慢等问题。

#### 勤劳方式：

*待添加*

## 分享阅读

[原文 @兔老表](https://weibo.com/3314845321/Lqw5ooJS2)

```
正经人谁怕公布IP呢
正经人谁穿成这样上街呢
正经人还怕被举报？
正经人谁看这些书和电影啊
正经人会这么说话吗
正经人会半夜还不回家？
正经人，要不你告诉我什么样才算正经人吧
```

[关于即将上线的显示ip属地功能，你有什么想说的？ - 感恩节快乐的回答 - 知乎](https://www.zhihu.com/question/528609532/answer/2447942947)（作者禁止转载）
