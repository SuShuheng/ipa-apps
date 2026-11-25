# shmarket

shmarket 是 SuShuheng 自制 iOS 和 iPadOS 应用的 SideStore 软件源。添加一次后，你可以在 SideStore 里浏览已上架的应用、安装 IPA，并在发布新版本后更新。

[![Release 附件累计下载量](https://img.shields.io/github/downloads/SuShuheng/ipa-apps/total?style=flat-square&label=Release%20%E6%80%BB%E4%B8%8B%E8%BD%BD%E9%87%8F&color=167D64)](https://github.com/SuShuheng/ipa-apps/releases)
[![最新正式发行版](https://img.shields.io/github/v/release/SuShuheng/ipa-apps?style=flat-square&label=%E6%9C%80%E6%96%B0%E5%8F%91%E8%A1%8C%E7%89%88&color=245FAD)](https://github.com/SuShuheng/ipa-apps/releases)
[![GitHub Stars](https://img.shields.io/github/stars/SuShuheng/ipa-apps?style=flat-square&label=GitHub%20Stars&logo=github&color=A46613)](https://github.com/SuShuheng/ipa-apps/stargazers)

下载量统计 GitHub Releases 中所有版本的附件下载次数。徽章随 GitHub 数据自动更新，显示可能受缓存影响。首个 Release 发布后，下载和版本徽章才会有发行数据。

## 添加到 SideStore

在已安装 SideStore 的 iPhone 或 iPad 上打开 [shmarket 主页](https://sushuheng.github.io/ipa-apps/)，点 **在 SideStore 中添加**。

也可以在 SideStore 的 **Sources → ＋** 中粘贴下方地址，或直接前往 [GitHub Releases](https://github.com/SuShuheng/ipa-apps/releases) 查看发行记录。

```text
https://sushuheng.github.io/ipa-apps/source.json
```

## 发布应用

1. 在 [GitHub Releases](https://github.com/SuShuheng/ipa-apps/releases) 中新建 Release，并把 IPA 作为附件上传。取得形如 `https://github.com/SuShuheng/ipa-apps/releases/download/<tag>/<file>.ipa` 的直接下载地址。
2. 在 `source.json` 的 `apps` 数组添加应用。填写 `name`、`bundleIdentifier`、`developerName`、`localizedDescription`、公开可访问的 `iconURL` 和 `versions`。Bundle ID 取自 IPA 的 `Info.plist`。
3. 在 `versions` 中填写 `version`、`buildVersion`、ISO 8601 格式的 `date`、`downloadURL` 和以字节为单位的 `size`。需要时可以填写 `minOSVersion` 和版本的 `localizedDescription`。发布更新时，将新版本放在数组开头，保留旧版本。
4. 提交到 `main` 后，GitHub Pages 会重新发布软件源。部署完成后，在 SideStore 中刷新。

GitHub Pages 从 `main` 分支根目录发布。字段说明见 [AltSource 格式](https://faq.altstore.io/developers/make-a-source) 和 [SideStore 软件源文档](https://docs.sidestore.io/docs/advanced/app-sources)。
