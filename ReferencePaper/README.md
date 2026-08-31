# ReferencePaper — 分类文献库

按主题分类存放全文 PDF。下载清单见 [../PAPERS_TO_DOWNLOAD.md](../PAPERS_TO_DOWNLOAD.md)。

## 分类

| 目录 | 收录内容 |
|---|---|
| `00_Reviews_Capacitor/` | 电容专门综述 —— **竞品**，用于 review-of-reviews 与 gap matrix |
| `01_Reviews_Adjacent/` | 相邻领域综述：变换器可靠性、器件监测、PIML、PHM 通论 |
| `02_Failure_Physics/` | 失效物理、退化机理、老化规律、加速老化实验 |
| `03_CM_ParameterEstimation/` | 在线/离线监测与 ESR·C·阻抗参数估计方法 |
| `04_SOH_RUL_Prognostics/` | SOH 估计、退化建模、RUL 预测、随机过程与滤波 |
| `05_DataDriven_AI/` | 机器学习 / 深度学习 / 迁移学习方法 |
| `06_PhysicsInformed_DigitalTwin/` | 物理信息机器学习、灰箱模型、数字孪生 |
| `07_Datasets_Standards/` | 公开数据集（如 NASA PCoE）、标准、EOL 判据 |

## 命名规范

```
<年份>_<第一作者姓>_<期刊简称>_<短标题>.pdf
```

例：`2024_Fassi_TPEL_PIML_PredictiveMaintenance_PowerConverters_Review.pdf`

一篇论文若跨类别，放主类别，不复制。

## 当前库存（3 篇，均为合法开放获取）

| 文件 | 来源通道 | OA 类型 |
|---|---|---|
| `00_Reviews_Capacitor/2020_Dang_Kwak_Sensors_HealthMonitoringCapacitors_Review.pdf` | MDPI CDN | Gold |
| `00_Reviews_Capacitor/2023_Ramees_Ahmad_IEEEAccess_CapacitorHealthMonitoring_Review.pdf` | IEEE Xplore OA 直链 | Gold |
| `01_Reviews_Adjacent/2014_Wang_Blaabjerg_TIA_ReliabilityDCLinkCapacitors_Overview.pdf` | Aalborg VBN 机构库 | Green/Bronze |

OA 状态经 Unpaywall API 确认后才下载；未确认为开放获取的一律不自行抓取，列入下载清单交由用户通过机构订阅获取。

## 本机网络限制（供后续参考）

| 站点 | 状态 |
|---|---|
| `hal.science` / `cea.hal.science` | 不可达（000）+ 反爬页 |
| `mdpi.com` | 403，但 `res.mdpi.com` CDN 可用 |
| `ieeexplore.ieee.org` | 418，但 `ielx7/…` OA 直链可用 |
| `sciencedirect.com` | 反爬页，AM 版本不可自动获取 |
| `vbn.aau.dk` | 可用 |
| `api.crossref.org` / `api.unpaywall.org` | 可用 |
