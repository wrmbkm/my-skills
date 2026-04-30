---
name: nvidia-version-tracker
description: Track NVIDIA infrastructure software versions. Triggers when user asks about NVIDIA software versions (CUDA, NCCL, DOCA-OFED, ConnectX-8 Firmware), checks for updates, or wants version reports. The skill queries NVIDIA/CUDA archives, GitHub API, NGC catalog, and NVIDIA networking docs to fetch latest versions and compare with recorded versions.
---

# NVIDIA Version Tracker

Track 4 key infrastructure components. When asked to check/update versions:

1. Run all queries in parallel (web_search/web_crawl/GitHub API)
2. Compare results with version archive (references/version-archive.md)
3. Report changes in Feishu doc format

## Components

| Component | Query Method |
|-----------|-------------|
| CUDA Toolkit | `web_crawl` → https://developer.nvidia.com/cuda-toolkit-archive |
| NCCL | `web_search` → GitHub API: https://api.github.com/repos/NVIDIA/nccl/releases/latest |
| DOCA-OFED | `web_crawl` → https://catalog.ngc.nvidia.com/orgs/nvidia/teams/mellanox/containers/doca-driver/tags |
| ConnectX-8 Firmware | See references/firmware-query.md |

## Output Format

- **有更新** → 输出飞书云文档格式（Markdown，可直接复制粘贴）
- **无更新** → 直接回复"未更新"

## Version Archive

All recorded versions are in `references/version-archive.md`. Read it first to know what to compare against.
