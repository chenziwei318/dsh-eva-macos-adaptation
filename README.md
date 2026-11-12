# DeepSeek Harness EVA macOS 适配补丁

本项目基于 [Iris-change/dsh-eva-skins](https://github.com/Iris-change/dsh-eva-skins) 2.1.6（提交 `2c57741`），提供 macOS 适配补丁。原项目的代码以 MIT 许可证发布；本仓库不包含原项目中单独授权的 EVA 图像、音频和其他资源。

- 保留 EVA 开机动画和号机选择，macOS 的聊天区、侧边栏和原有壁纸不套用 EVA 颜色和覆盖层。
- 动画退出时立即释放鼠标事件；防卡住的超时保护不会被动画进度消息取消。
- 在动画中按 Escape 可退出；插件停用时清理动画和装饰层。

## 使用

先取得原项目 2.1.6 的源码，再在其仓库目录应用本补丁：

```sh
git clone https://github.com/Iris-change/dsh-eva-skins.git
cd dsh-eva-skins
git checkout 2c57741
git apply /path/to/macos.patch
```

将 `/path/to/macos.patch` 替换为本补丁文件的实际路径。按原项目说明使用 DeepSeek Harness 插件管理器安装这个本地目录，然后彻底退出并重新打开 DeepSeek Harness。本地目录需保留，删除后插件会失效。

## 验证范围

针对遮罩退出、iframe 内 Escape、超时保护、插件卸载清理与 macOS 原配色进行浏览器模拟验证，并在 macOS 的 DeepSeek Harness 0.2.2-rc.2 上检查启动画面。修改只影响插件，不更改 DeepSeek Harness 主程序。
