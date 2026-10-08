# 猫猫币 MMC · Super 共享节点

纯静态 HTML/CSS/JavaScript 页面，可直接部署到 GitHub Pages。打开页面后，在“节点设置”中填入真实 Super 共享节点公开的 HTTPS JSON-RPC 地址，页面会从浏览器直接请求节点。

## Super 节点 RPC 约定

页面默认尝试调用：

- `mmc_getSyncStatus` → `{ height, synced }`
- `mmc_startMining` → 开始挖矿

余额、私钥派生、本地签名和 `mmc_sendRawTransaction` 需要 Super 节点明确协议后继续接入。未配置或连接失败时，页面显示带明确标识的演示数据，不伪造真实链上结果。

## 安全

私钥只存在当前标签页内存中，刷新后清除；不会进入 localStorage、不会上传到 Super 节点，也不会写入页面文件。生产环境建议使用硬件钱包或专用本地签名库。

## GitHub Pages

在 GitHub 仓库 **Settings → Pages** 中选择 `Deploy from a branch`，分支选择 `main` / `/ (root)`。页面无需构建步骤。
