# 微博境外势力

使用您的规则代理工具，在微博上成为境外势力。

> 此项目目前支持：
 * [Clash for Windows](#ClashForWindows)
 * [Shadowrocket](#Surge)
 * [Surge](#Surge)
 * 欢迎 Pull Request 添加更多规则工具
<!-- * [Quantumult X](#QuantumultX) -->
---

## 前情提要

[IP属地功能升级公告 — @微博管理员](https://weibo.com/1934183965/LqvYeCdBu) （[文字版本](./IP%E5%B1%9E%E5%9C%B0%E5%8A%9F%E8%83%BD%E5%8D%87%E7%BA%A7%E5%85%AC%E5%91%8A.md)）

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

保存并关闭您的文本编辑器。然后在 Profiles 中，重新刷新您的订阅。规则会自动应用到更新后的订阅。

如果您正在使用其它的配置 Parser，您也可以将以上三个规则添加到 `prepend-rules` 的最顶端。
<!-- ### <a id="QuantumultX"> -->

### <a id="Surge"> Surge/Shadowrocket </a>

在 Surge/Shadowrocket 客户端中，导入并启用以下模块。

`link`

或是手动创建新模块，并粘贴以下内容：

```conf
[Rule]
DOMAIN-SUFFIX,weibo.com,PROXY
DOMAIN-SUFFIX,weibo.cn,PROXY
DOMAIN-SUFFIX,weico.cc,PROXY
```

---

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