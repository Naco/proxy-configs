# 微博净化[墨鱼版] Surge 模块

## 安装

复制以下 URL，在 Surge 模块管理中通过 URL 安装并启用：

text
https://raw.githubusercontent.com/Naco/proxy-configs/main/surge/modules/WeiboEnhanced.sgmodule


确保主配置已经可以工作，脚本/重写和 MITM 已启用，MITM 证书已安装并信任。检查原作者脚本下载是否成功。该模块无需另外下载 JS 文件。

在 Safari 打开 https://api.weibo.cn/__qx_weibo_settings__/ 读取和调整设置，保存后返回微博刷新。如已有其他微博净化模块，先停用重叠模块，以免首条匹配脚本优先导致部分规则不生效。

停用或移除模块即可停止其规则；保存的设置可能仍留在 Surge 本地存储中。圈 X 的设置不会自动迁移到 Surge。

## 转换范围

- 原配置的 6 条规则及 4 个 MITM 域名完整保留，hostname 使用 %APPEND% 追加。
- 设置页与配置读取转换为 http-request；保存/重置请求开启 requires-body。
- 响应净化转换为 http-response，并开启 requires-body。
- 原脚本内置 Surge 运行时适配，未修改或重新分发原作者脚本。
- 响应处理上限为 5 MiB，超过后 Surge 跳过脚本、原样放行；设置写入请求上限为 1 MiB，脚本自身另有配置长度限制。
- 继续使用作者的远程脚本，保留自动更新；以后行为可能随脚本更新变化。

## 验证记录

日期：2026-10-30（中国标准时间）。配置基线 V0.1.21；脚本基线 0.1.52。

已通过设置页响应形状、配置读取/保存/重置、持久存储回读、无效写请求拦截、全部 31 个接口的路径匹配和边界检查、未知响应格式下的 QX/Surge 模拟结果对比、无效 JSON 原样返回检查，共执行 131 次模拟脚本调用。

未在真实 Surge 或 iPhone 上运行，未使用真实微博流量。模拟验证不能证明某个已安装微博版本的所有广告与界面净化效果。

核对时脚本 SHA-256：

text
0bb38335cb0cda1ba0003ef44d4e0a4aa98925f11d5a6aa4ec4a765d08c5df41


## 来源

- 原配置与脚本作者：@ddgksf2013；原配置贡献者：@zmqcherish。
- 原配置：https://ddgksf2013.top/rewrite/WeiboEnhanced.conf
- 原脚本：https://ddgksf2013.top/scripts/weibo_json.js
- Surge 请求脚本：https://manual.nssurge.com/scripting/http-request.html
- Surge 响应脚本：https://manual.nssurge.com/scripting/http-response.html

上游来源与作者信息保留在模块头部；此格式转换不改变上游作品的权利归属。
