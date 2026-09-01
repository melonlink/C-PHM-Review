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

## 当前库存（12 篇，全部已完成文本提取与身份核验）

| 目录 | 篇数 | 内容 |
|---|---:|---|
| `00_Reviews_Capacitor/` | 5 | Soliman 2016 · Dang 2020 · Nathan 2023 · Ramees 2023 · Yu 2025 |
| `01_Reviews_Adjacent/` | 3 | Yang 2010 · Wang & Blaabjerg 2014 · **Fassi 2024** |
| `02_Failure_Physics/` | 1 | Torki 2023 |
| `03_CM_ParameterEstimation/` | 3 | Li 2022 · Wang 2025 · Yamasoto 2025 |

身份核验：9 篇用户下载的论文中 8 篇由正文内 DOI 自动比对通过；D08（Wang 2025）为 TPEL Letters，正文不印 DOI，已按卷期页 40(8) 10385 + 标题 + 作者比对确认。

其中 3 篇由本会话经 Unpaywall 确认 OA 后自行下载（Dang 2020 走 MDPI CDN，Ramees 2023 走 IEEE OA 直链，Wang 2014 走 Aalborg VBN）。

## 本机网络限制（供后续参考）

| 站点 | 状态 |
|---|---|
| `hal.science` / `cea.hal.science` | 不可达（000）+ 反爬页 |
| `mdpi.com` | 403，但 `res.mdpi.com` CDN 可用 |
| `ieeexplore.ieee.org` | 418，但 `ielx7/…` OA 直链可用 |
| `sciencedirect.com` | 反爬页，AM 版本不可自动获取 |
| `vbn.aau.dk` | 可用 |
| `api.crossref.org` / `api.unpaywall.org` | 可用 |
