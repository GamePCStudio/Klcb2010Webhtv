# Klcb2010Webhtv

基于 [klcb2010/webhtv](https://github.com/klcb2010/webhtv) 的派生构建项目。

## 改动

- **包名**：`com.fongmi.android.tv` → `com.Klcb.android.webhtv`
- **App 名称**：`TV` → `K影视`
- **只构建 TV（leanback）版**：`arm64-v8a` + `armeabi-v7a`
- 编译出的 release APK 使用 debug 密钥签名，可直接 sideload 安装到电视/盒子

## 工作原理

本仓库不含完整源码（上游仓库约 575MB，含本地 media3 / mpv 预编译依赖）。
构建由 GitHub Actions 完成：每次 push 到 `main` 或手动 `workflow_dispatch` 时，
工作流会：

1. 克隆 `klcb2010/webhtv` 最新代码（即“同步”）
2. 自动改写包名与 App 名称
3. 仅编译 leanback（TV）版两个 ABI
4. 把 APK 作为 artifact 上传，供下载

## 下载 TV 版 APK

进入仓库 **Actions → Build TV (Klcb2010Webhtv)** → 最新运行 → 底部 **Artifacts → tv-apks**
下载即可（仅含 TV 版，不含 mobile 版）。
