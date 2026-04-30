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

## 当前记录版本（2026-04-24）

| 软件 | 版本号 | 类型 | 发布日期 |
|------|--------|------|---------|
| CUDA | 13.2 (Update 1) | 标准补丁版 | 2026-03-05 |
| NCCL | 2.30.4-1 | GA | 2026-04-22 |
| DOCA-OFED | 26.01（随 DOCA 3.3.0）| GA | 2026-02-24 |
| MFT | v4.35.0-159 | GA | ~2026-03-02 |
| ConnectX-8 Firmware | v40.48.1000（GA）/ v40.47.1088（LTS）| GA / LTS U5 | 2026-02 / ~2026-04 |

## 版本选择说明
- ConnectX-8 Firmware 长期维护双分支并行：
  - **v40.48.1000**：新功能分支，2026 年 2 月 MFT v4.35.0 GA 捆绑，Spectrum-X 2.1 验证通过，Gen6+GPU 混合部署必须用
  - **v40.47.1088**：LTS 安全补丁分支，2026 年 4 月更新，含 Lane Margin 等新诊断功能；高于之前记录的 v40.47.2682
- 两者同属活跃分支，40.48 是 2026 年新开的 GA 分支
