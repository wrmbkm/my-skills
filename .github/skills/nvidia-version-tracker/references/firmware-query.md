# ConnectX-8 固件查询方法

> ⚠️ NVIDIA Docs 页面是动态渲染，爬取内容会被截断。需直接访问具体版本号的文档 URL。

## 查询流程

### 第一步：查 MFT 最新 GA 版本

访问 MFT 版本列表页：
```
https://docs.nvidia.com/networking/display/mftv<version>/changes-and-new-features
```

- MFT GA 分支版本结构为 `mftv<major><minor>`（如 mftv4350 = v4.35.0）
- 找最大的主版本号，即为当前最新 MFT GA
- **正确方式**：直接访问具体版本号 URL（如 mftv4350）获取完整信息

### 第二步：查该 MFT 捆绑的 ConnectX-8 固件版本

```
https://docs.nvidia.com/networking/display/mftv4350/supported-adapter-cards-firmware-versions
```

- 表格中 ConnectX-8 行即为当前最新 GA 分支固件版本
- 记录格式：`vXX.XX.XXXX`（如 v40.48.1000）

### 第三步：查 LTS 分支是否有更新补丁

方法 A：在 Adapter Firmware 下载中心页面搜索 `connectx8firmwarev4047` 最新子版本

方法 B：直接访问已知的 LTS 版本 URL 确认日期：
```
https://docs.nvidia.com/networking/display/connectx8firmwarev40472682lts
```

## 关键教训

- **NVIDIA Docs 页面（含 Adapter Firmware 等）是动态渲染**：爬取内容会被截断，需直接访问具体版本号的文档 URL
- **ConnectX-8 固件追踪**：通过 MFT 最新 GA 捆绑版本间接获取，跳过 Adapter Firmware 动态渲染页
