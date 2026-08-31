# 需要您下载的论文清单 / Papers to Obtain

**日期：** 2026-08-30 · **机读版本：** [02_literature/papers_to_obtain.csv](02_literature/papers_to_obtain.csv)

所有 DOI 均已通过 **Crossref API 逐条核验**（DOI → 标题/作者/期刊/卷期页/年份全部匹配）。清单中没有任何推测或臆造的 DOI —— 核验过程中我尝试凭记忆重建的 2 个 DOI 返回 404，已直接剔除而非猜测填入。

下载后请放入对应的 `目标文件夹` 列所指目录，文件名建议沿用 `建议文件名` 列。

---

## 我已经下载好的（3 篇，开放获取）

| 文件 | 位置 |
|---|---|
| Wang & Blaabjerg 2014, IEEE TIA（经 Aalborg 机构库 VBN） | `ReferencePaper/01_Reviews_Adjacent/` |
| Dang & Kwak 2020, Sensors（经 MDPI CDN，金色 OA） | `ReferencePaper/00_Reviews_Capacitor/` |
| Muhammed Ramees & Ahmad 2023, IEEE Access（金色 OA） | `ReferencePaper/00_Reviews_Capacitor/` |

---

## P0 — 阻塞 Stage 0 收尾（5 篇，请优先）

> **D02 与 D03 是唯二可能改变创新性判定结论的两篇**，其余三篇只会细化 gap matrix。

| # | DOI | 标题 | 期刊 / 卷期页 | 平台 | 为什么必须要 | 目标文件夹 |
|---|---|---|---|---|---|---|
| **D03** | `10.1109/TPEL.2025.3571897` | Review of Health Monitoring Techniques for Capacitors in Modular Multilevel Converters | IEEE TPEL **40(9) 13363–13382**, 2025 | IEEE Xplore | **最高优先级。** 目标期刊 2025 年 9 月刚发的电容监测综述，直接决定 TPEL 的选题饱和风险 | `ReferencePaper/00_Reviews_Capacitor/` |
| **D02** | `10.1109/TPEL.2023.3328438` | Toward Physics-Informed Machine-Learning-Based Predictive Maintenance for Power Converters — A Review | IEEE TPEL **39(2) 2692–2720**, 2024 | IEEE Xplore | **最强竞品。** 同一期刊，2 年 138 引，已占据 physics-informed 框架。必须精读以精确划定差异化边界 | `ReferencePaper/01_Reviews_Adjacent/` |
| D01 | `10.1109/TIA.2016.2591906` | A Review of the Condition Monitoring of Capacitors in Power Electronic Converters | IEEE TIA 52(6) 4976–4989, 2016 | IEEE Xplore | 领域基础分类法（262 引）。需全文确认其确无 SOH/RUL 层级，才能坐实我们的 gap 主张 | `ReferencePaper/00_Reviews_Capacitor/` |
| D04 | `10.1016/j.microrel.2023.115003` | Review of condition monitoring methods for capacitors used in power converters | Microelectron. Reliab. 145, 115003, 2023 | Elsevier ScienceDirect | 唯一涉及 ANN 预测性维护的电容综述，需评估其 RUL/ML 深度 | `ReferencePaper/00_Reviews_Capacitor/` |
| D05 | `10.1016/j.est.2022.106330` | Electrolytic capacitor: Properties and operation | J. Energy Storage 58, 106330, 2023 | Elsevier ScienceDirect | 第 2 章退化物理的骨架（铝电解老化规律）。HAL 上有绿色 OA，但本机无法访问 hal.science | `ReferencePaper/02_Failure_Physics/` |

**建议文件名**

```
D01  2016_Soliman_TIA_ConditionMonitoringCapacitors_Review.pdf
D02  2024_Fassi_TPEL_PIML_PredictiveMaintenance_PowerConverters_Review.pdf
D03  2025_Yu_TPEL_CapacitorHealthMonitoring_MMC_Review.pdf
D04  2023_Nathan_MicroRel_CapacitorConditionMonitoring_Review.pdf
D05  2023_Torki_JEnergyStorage_ElectrolyticCapacitor_PropertiesOperation.pdf
```

---

## P1 — Stage 1 起步用（4 篇，不阻塞当前判定）

| # | DOI | 标题 | 期刊 / 卷期页 | 用途 | 目标文件夹 |
|---|---|---|---|---|---|
| D06 | `10.1109/TPEL.2010.2049377` | Condition Monitoring for Device Reliability in Power Electronic Converters: A Review | IEEE TPEL 25(11) 2734–2752, 2010 | 全领域 1137 引锚点，用于 Fig.1 演进时间轴的起点 | `ReferencePaper/01_Reviews_Adjacent/` |
| D07 | `10.1109/TPEL.2021.3092429` | Online Condition Monitoring of DC-Link Capacitor for AC/DC/AC PWM Converter | IEEE TPEL 37(1) 865–878, 2022 | 复用既有传感器的在线估计代表作，可部署性坐标锚点 | `ReferencePaper/03_CM_ParameterEstimation/` |
| D08 | `10.1109/TPEL.2025.3556740` | An Online DC-Link Capacitor Condition Monitoring Method for CHB-Type SVG | IEEE TPEL 40(8) 10385–10390, 2025 | 2025 最新在线 CM，检验领域是否已越过"参数估计" | `ReferencePaper/03_CM_ParameterEstimation/` |
| D09 | `10.1016/j.microrel.2025.115873` | Condition monitoring of a DC-link capacitor in an inverter with a front-end diode rectifier under imbalanced conditions | Microelectron. Reliab. 173, 115873, 2025 | 2025 工作点鲁棒性（不平衡工况）证据 | `ReferencePaper/03_CM_ParameterEstimation/` |

**建议文件名**

```
D06  2010_Yang_TPEL_ConditionMonitoringDeviceReliability_Review.pdf
D07  2022_Li_TPEL_OnlineCM_DCLinkCapacitor_PWMConverter.pdf
D08  2025_Wang_TPEL_OnlineCM_DCLinkCapacitor_CHB_SVG.pdf
D09  2025_Yamasoto_MicroRel_DCLinkCapacitorCM_ImbalancedConditions.pdf
```

---

## 下载说明

- **IEEE 平台（D01/D02/D03/D06/D07/D08）** — 请在 IEEE Xplore 用机构权限下载。直接拼 DOI 即可打开：`https://doi.org/<DOI>`
- **Elsevier / ScienceDirect（D04/D05/D09）** — 同样用 `https://doi.org/<DOI>` 进入。
- 本机网络状况：`hal.science` 完全不可达（返回 000），`mdpi.com` 与 `ieeexplore.ieee.org` 有反爬拦截（403 / 418）。IEEE Access 的金色 OA 直链与 Aalborg 机构库 VBN 可用 —— 后续若还有 OA 论文，我会优先走这两条通道自行下载，不再麻烦您。

## ReferencePaper 分类结构

```
ReferencePaper/
├─ 00_Reviews_Capacitor/          电容专门综述（竞品）
├─ 01_Reviews_Adjacent/           相邻领域综述（变换器可靠性 / PIML / PHM）
├─ 02_Failure_Physics/            失效物理与退化机理
├─ 03_CM_ParameterEstimation/     在线监测与参数估计方法
├─ 04_SOH_RUL_Prognostics/        SOH 估计与 RUL 预测
├─ 05_DataDriven_AI/              数据驱动 / 机器学习方法
├─ 06_PhysicsInformed_DigitalTwin/ 物理信息机器学习 / 数字孪生
└─ 07_Datasets_Standards/         公开数据集与标准
```
