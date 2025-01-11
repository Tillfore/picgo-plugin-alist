## picgo-plugin-alist

plugin for picgo

通过alist实现对oneDrive、阿里云盘、天翼云盘、GoogleDrive、夸克网盘、迅雷云盘等的文件上传，并通过alist实现直链获取（alist可以处理动态直链问题），最终达成对上述各网盘的图床实现。

支持alist `v2`和`v3`版本。

## alist简介

[alist](https://github.com/alist-org/alist)是一个支持多存储的文件列表程序，使用 `Gin` 和 `Solidjs`。使用alist可以利用OneDrive等网盘快速搭建一个下载站。
![](/readme/alist.png)

## 参数

| key         | 是否必填 | description                                                                    | example                   |
| ----------- | -------- | ------------------------------------------------------------------------------ | ------------------------- |
| alist版本   | √        | 2或者3                                                                         | 3                         |
| alist地址   | √        | 你的alist地址                                                                  | https://alist.example.com |
| 上传路径    | √        | 上传的相对路径（alist内的路径，根据路径上传到对应网盘）                        | assets                    |
| 管理员token | √        | 管理员token([参考alist文档](https://alist-doc.nn.ci/docs/driver/alist/#token)) | balabala                  |
| 访问路径    | ×        | 公开的访问路径（资源最终链接，默认同上传路径）                                 | public                    |

## 说明
### 高版本签名

高版本alist加入了“签名”特性，并默认开启“签名所有”。改选项打开后，会向所有文件的直接链接添加签名(无论是否有密码)。
如果遇到代码401错误，请在alist设置中关闭“签名所有”（Alist管理-设置-全局-签名所有）。
![](/readme/sign_off.png)
- 目前尝试仿照alist源码进行签名，但签名并不一致（失败~）。

## 安装

- 在线安装
    打开 [PicGo](https://github.com/Molunerfinn/PicGo) 详细窗口，选择`插件设置`，搜索`alist`安装。

- 离线安装
  克隆该项目，复制项目到 以下目录：
  - Windows: `%APPDATA%\picgo\`
  - Linux: `$XDG_CONFIG_HOME/picgo/` or `~/.config/picgo/`
  - macOS: `~/Library/Application\ Support/picgo/`

  切换到新目录执行 `npm install ./picgo-plugin-alist`，然后重启应用即可。
