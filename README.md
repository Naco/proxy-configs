# 远程配置仓库

给手机和电脑上的 Surge、Clash Verge Rev、Sparkle 等客户端存放远程配置、规则与模块。仓库公开，客户端可通过稳定的原始文件 URL 拉取更新。

## 可以直接使用的资源

| 客户端 | 资源 | 复制到客户端的 URL |
| --- | --- | --- |
| Surge | 微博净化[墨鱼版]模块 | https://raw.githubusercontent.com/Naco/proxy-configs/main/surge/modules/WeiboEnhanced.sgmodule |

Surge：在「模块」中通过 URL 安装上面的地址并启用。该资源是功能模块，需要已有的 Surge 主配置；它不提供代理节点。开启脚本/重写与 MITM，并安装、信任 Surge 的 MITM 证书后使用。

微博助手设置页：https://api.weibo.cn/__qx_weibo_settings__/ 。该页面由已启用的模块在本地响应，保存后回到微博刷新。

## 目录

- surge/modules/：Surge 模块。
- clash-verge-rev/：Clash Verge Rev 配置与规则，待添加。
- sparkle/：Sparkle 配置与规则，待添加。
- docs/：使用和验证说明。

目前可以订阅的资源只有表格中的 Surge 微博模块。sgmodule 不能直接作为 Clash Verge Rev 或 Sparkle 的配置使用；后续按各客户端支持的格式添加，并把可用 URL 加到表格。

## 更新约定

客户端使用 raw.githubusercontent.com 链接，不使用 GitHub 的 blob 网页地址。保持文件路径稳定，后续更新覆盖同一路径。

本仓库公开：代理节点密码、私人订阅链接、订阅令牌、API 密钥、MITM 私钥与证书等保存在客户端或本地私有文件中，不提交到本仓库。

## 来源与验证

微博配置和脚本原作者：[@ddgksf2013](https://github.com/ddgksf2013)，原配置贡献者 @zmqcherish。原配置：https://ddgksf2013.top/rewrite/WeiboEnhanced.conf 。本仓库只提供 Surge 规则格式转换，仍引用原作者脚本并保留更新。

基线为配置 V0.1.21、脚本 0.1.52，核对日期 2026-10-30（中国标准时间）。已完成本地模拟验证，真实 Surge / 微博设备效果待验证，详见 [微博模块说明](docs/weibo-surge.md)。
