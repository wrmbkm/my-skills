# NVIDIA Version Archive

> 记录最新版本信息。有更新时更新此文件。

## 版本存档页面

| 软件 | 页面 | 推荐查询方式 |
|------|------|------------|
| CUDA Toolkit | https://developer.nvidia.com/cuda-toolkit-archive | 访问存档页锚点 #cuda-13-2-0 确认最新小版本 |
| NCCL | https://api.github.com/repos/NVIDIA/nccl/releases/latest | **GitHub API**（返回 JSON，含 tag_name / published_at / body） |
| DOCA-OFED | https://catalog.ngc.nvidia.com/orgs/nvidia/teams/mellanox/containers/doca-driver/tags | NGC 容器镜像标签页，最新标签即最新版本组合 |
| 网卡 Firmware | 见 firmware-query.md | 见下方查询方法 |

## ConnectX-8 固件查询方法

**第一步：查 MFT 最新 GA 版本**
- MFT 版本列表页：`https://docs.nvidia.com/networking/display/mftv<version>/changes-and-new-features`
- MFT GA 分支版本结构为 `mftv<major><minor>`（如 mftv4350 = v4.35.0）
- 找最大的主版本号，即为当前最新 MFT GA

**第二步：查该 MFT 捆绑的 ConnectX-8 固件版本**
- URL：`https://docs.nvidia.com/networking/display/mftv4350/supported-adapter-cards-firmware-versions`
- 表格中 ConnectX-8 行即为当前最新 GA 分支固件版本

**第三步：查 LTS 分支是否有更新补丁**
- 在 Adapter Firmware 下载中心页面搜索 `connectx8firmwarev4047` 最新子版本
- 或直接访问已知的 LTS 版本 URL（如 40.47.2682）确认日期有无更新

## 当前记录版本（2026-05-29）

| 软件 | 版本号 | 类型 | 发布日期 |
|------|--------|------|---------|
| CUDA | 13.2 (Update 1) | 标准补丁版 | 2026-05-12 |
| NCCL | 2.30.4-1 | GA | 2026-02-26 |
| DOCA-OFED | 26.04.0（随 DOCA 3.3.1）| GA | 2026-05（Release Notes 月份） |
| MFT | v4.35.0-160 | GA | ~2026-05（官网页面未单独标注发布日期） |
| ConnectX-8 Firmware | v40.48.1000（GA）/ v40.47.3006（LTS）| GA / LTS | 2026-02（官方 release notes 仅标月） / 2026-05-05 |

> 2026-05-29 复核：发现 DOCA-OFED、MFT、ConnectX-8 Firmware（LTS）有更新，已同步到上述记录；NCCL 与 CUDA 版本号无变化。

## 版本选择说明
- ConnectX-8 Firmware 长期维护双分支并行：
  - **v40.48.1000**：GA 新功能分支，官方 release notes 页面日期为 2026-02（页面仅标月）
  - **v40.47.3006**：LTS 分支新补丁版本（高于 v40.47.2682），官方页面日期为 2026-05-05
- 两者同属活跃分支，40.48 是 2026 年新开的 GA 分支
