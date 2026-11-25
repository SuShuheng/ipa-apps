# shmarket

SuShuheng 自制 iOS 和 iPadOS 应用的 SideStore 软件源。

- [软件源主页](https://sushuheng.github.io/ipa-apps/)
- [软件源地址](https://sushuheng.github.io/ipa-apps/source.json)

在 SideStore 中打开 **Sources → ＋**，粘贴软件源地址即可订阅。

## 发布应用

1. 在 [GitHub Releases](https://github.com/SuShuheng/ipa-apps/releases) 中新建 Release，并把 IPA 作为附件上传。取得形如 `https://github.com/SuShuheng/ipa-apps/releases/download/<tag>/<file>.ipa` 的直接下载地址。
2. 在 `source.json` 的 `apps` 数组添加应用。填写 `name`、`bundleIdentifier`、`developerName`、`localizedDescription`、公开可访问的 `iconURL` 和 `versions`。Bundle ID 取自 IPA 的 `Info.plist`。
3. 在 `versions` 中填写 `version`、`buildVersion`、ISO 8601 格式的 `date`、`downloadURL` 和以字节为单位的 `size`。需要时可以填写 `minOSVersion` 和版本的 `localizedDescription`。发布更新时，将新版本放在数组开头，保留旧版本。
4. 提交到 `main` 后，GitHub Pages 会重新发布软件源。部署完成后，在 SideStore 中刷新。

GitHub Pages 从 `main` 分支根目录发布。字段说明见 [AltSource 格式](https://faq.altstore.io/developers/make-a-source) 和 [SideStore 软件源文档](https://docs.sidestore.io/docs/advanced/app-sources)。
