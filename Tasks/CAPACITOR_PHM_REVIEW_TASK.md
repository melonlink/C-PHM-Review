# Capacitor PHM Review —— 综述研究与论文执行任务书

> **项目文件夹建议：** `Capacitor_PHM_Review`  
> **任务性质：** 文献调研 + 创新性查重 + 系统综述框架构建 + 论文素材库建立  
> **目标：** 形成一篇面向 2026 年研究现状、具有明确方法学创新视角的高质量电力电子电容 PHM 综述  
> **核心原则：** 不再重复传统“ESR / 电容量在线监测方法罗列”，而是建立从退化物理到预测性维护的完整 PHM 技术链条。

---

# 1. 研究目标

本项目拟围绕**电力电子变换器中电容器的健康监测、故障诊断、健康状态估计和剩余寿命预测**开展系统综述。

论文不应停留在传统的：

- ESR 估计；
- Capacitance 估计；
- 阻抗测量；
- 温度监测；
- 某几种在线检测方法对比。

而应建立完整的：

```text
Failure Physics
      ↓
Degradation Mechanisms
      ↓
Health Indicators
      ↓
Online Parameter Estimation
      ↓
Fault / Degradation Diagnosis
      ↓
SOH Estimation
      ↓
RUL Prediction
      ↓
Prognostics & Health Management
      ↓
Predictive Maintenance
```

最终回答一个核心问题：

> **电容健康管理技术如何从“参数监测”发展为“面向真实电力电子系统的可部署 PHM”？**

---

# 2. 建议论文定位

## 2.1 推荐主标题

### Option A —— 首选

**Capacitor Prognostics and Health Management in Power Electronic Converters: From Physics-Based Monitoring to Data-Driven and Physics-Informed Intelligence**

### Option B

**From Condition Monitoring to Prognostics and Health Management of Capacitors in Power Electronic Converters: A Review**

### Option C

**Health Monitoring, Diagnosis, and Prognostics of Capacitors in Power Electronic Converters: Methods, Deployability, and Future Directions**

在完成文献查重后，再决定最终标题。

---

# 3. 与已有综述的差异化要求

Agent 必须首先完成“综述的综述（Review of Reviews）”，证明本文有新的综述价值。

至少重点分析以下代表性综述：

1. **Soliman, Wang, Blaabjerg, 2016**
   - *A Review of the Condition Monitoring of Capacitors in Power Electronic Converters*
   - IEEE Transactions on Industry Applications
   - 52(6): 4976–4989
   - DOI: `10.1109/TIA.2016.2591906`

2. **Dang, Kwak, 2020**
   - *Review of Health Monitoring Techniques for Capacitors Used in Power Electronics Converters*
   - Sensors, 20(13), 3740
   - DOI: `10.3390/s20133740`

3. **Nathan et al., 2023**
   - *Review of condition monitoring methods for capacitors used in power converters*
   - Microelectronics Reliability, 145, 115003
   - DOI: `10.1016/j.microrel.2023.115003`

4. **Muhammed Ramees, Ahmad, 2023**
   - *Advances in Capacitor Health Monitoring Techniques for Power Converters: A Review*
   - IEEE Access, 11, 133540–133576
   - DOI: `10.1109/ACCESS.2023.3336986`

5. **Yu et al., 2025**
   - *Review of Health Monitoring Techniques for Capacitors in Modular Multilevel Converters*
   - IEEE Transactions on Power Electronics
   - 40(9): 13363–13382
   - DOI: `10.1109/TPEL.2025.3571897`

6. **Electrolytic capacitor: Properties and operation, 2023**
   - Journal of Energy Storage, 58, 106330
   - DOI: `10.1016/j.est.2022.106330`
   - 用于补充电解电容退化机理、老化规律和预测维护方面的综述背景。

---

# 4. 第一阶段必须回答的问题：我们还能综述什么？

在正式写论文之前，Agent 必须制作：

`review_of_reviews.md`

以及：

`review_gap_matrix.csv`

至少包含如下字段：

| 字段 | 内容 |
|---|---|
| Review | 已发表综述 |
| Year | 年份 |
| Journal | 期刊 |
| Capacitor Type | 电容类型 |
| Converter Type | 变换器范围 |
| Failure Physics | 是否覆盖退化物理 |
| ESR | 是否覆盖 |
| Capacitance | 是否覆盖 |
| Impedance | 是否覆盖 |
| Temperature | 是否覆盖 |
| Online Estimation | 是否覆盖 |
| Fault Diagnosis | 是否覆盖 |
| SOH | 是否覆盖 |
| RUL | 是否覆盖 |
| Physics-based | 是否覆盖 |
| Data-driven | 是否覆盖 |
| Physics-informed | 是否覆盖 |
| Digital Twin | 是否覆盖 |
| Uncertainty | 是否覆盖不确定性 |
| Embedded Deployment | 是否讨论嵌入式实现 |
| Additional Sensors | 是否需要额外传感器 |
| Intrusiveness | 是否讨论侵入性 |
| Industrial Deployability | 是否讨论产业部署 |
| Main Taxonomy | 原论文分类方法 |
| Main Limitation | 该综述的主要缺口 |

完成此表后，才允许确定论文最终创新定位。

---

# 5. 本综述建议提出的核心新框架

本文不建议再按照：

> Buck / Boost / Inverter / MMC

或者：

> ESR method / Capacitance method

进行单一分类。

建议建立一个**多维 PHM taxonomy**。

---

# 6. 第一维：PHM 技术演进五层框架

## Generation 1 — Direct Health-Parameter Monitoring

核心对象：

- ESR；
- Capacitance；
- tanδ；
- impedance；
- ripple；
- temperature；
- leakage current。

重点研究：

- 测量精度；
- 温度/频率依赖；
- 离线/在线测量；
- 是否需要额外硬件。

---

## Generation 2 — Online Model-Based Parameter Estimation

包含：

- circuit-model-based estimation；
- RLS；
- EKF / UKF；
- observer；
- state estimation；
- recursive identification；
- signal injection；
- ripple-based estimation；
- transient-response estimation；
- converter inherent excitation。

重点评价：

> 能否利用已有电压、电流传感器完成估计？

---

## Generation 3 — Degradation Modeling and Prognostics

包含：

- empirical degradation model；
- Arrhenius-type model；
- electro-thermal aging model；
- degradation-state model；
- Bayesian estimation；
- Kalman / particle filtering；
- stochastic degradation process；
- Wiener / Gamma process；
- SOH estimation；
- RUL prediction。

---

## Generation 4 — Data-Driven PHM

包含：

- PCA / statistical learning；
- SVM；
- Random Forest；
- XGBoost；
- ANN / MLP；
- CNN；
- RNN；
- LSTM / GRU；
- autoencoder；
- Transformer；
- self-supervised learning；
- anomaly detection。

需要特别回答：

1. 数据从哪里来？
2. 是否为 accelerated aging 数据？
3. 是否真实变换器运行数据？
4. 是否存在跨工作点泛化？
5. 是否能够跨不同型号电容迁移？
6. 是否只是在实验室数据集上取得高精度？

---

## Generation 5 — Physics-Informed / Hybrid / Intelligent PHM

重点检索：

- physics-informed machine learning；
- hybrid physics-data model；
- digital twin；
- electro-thermal digital twin；
- grey-box model；
- physics-guided neural network；
- transfer learning；
- domain adaptation；
- uncertainty-aware prediction；
- Bayesian deep learning；
- federated / edge PHM；
- foundation-model / time-series foundation model 在器件 PHM 中的潜在应用。

这一部分应成为 2026 年视角下的重要前沿章节。

---

# 7. 第二维：从监测到 PHM 的功能层级

所有论文应进一步打标签：

```text
Level 0  Measurement
Level 1  Health Indicator Extraction
Level 2  Parameter Estimation
Level 3  Fault / Degradation Detection
Level 4  Fault Identification / Severity Estimation
Level 5  SOH Estimation
Level 6  RUL Prediction
Level 7  Maintenance Decision
```

Agent 必须判断：

> 一篇论文到底只是“检测 ESR”，还是已经真正进入 SOH / RUL / PHM？

不能把简单参数估计统一称为 PHM。

---

# 8. 第三维：退化物理

建议按不同电容器分别建立退化链。

## 8.1 Aluminum Electrolytic Capacitor

关注：

- electrolyte evaporation；
- electrolyte degradation；
- oxide degradation；
- pressure / gas generation；
- temperature acceleration；
- ripple-current-induced heating；
- ESR increase；
- capacitance decrease；
- leakage current variation。

形成：

```text
Electrical / Thermal Stress
        ↓
Electrolyte / Dielectric Degradation
        ↓
ESR ↑ / C ↓ / Leakage Change
        ↓
Thermal Loss ↑
        ↓
Further Aging
        ↓
Failure
```

---

## 8.2 Metallized Film Capacitor

关注：

- self-healing；
- metallization loss；
- dielectric degradation；
- partial discharge；
- humidity；
- thermal aging；
- capacitance loss；
- ESR / dissipation factor evolution。

---

## 8.3 MLCC / Ceramic Capacitor

根据文献数量决定篇幅，重点关注：

- dielectric aging；
- cracking；
- DC bias；
- thermal-mechanical stress；
- insulation degradation。

---

# 9. 第四维：工程可部署性

这是本综述建议重点强化的维度。

对每一种方法必须评价：

## 9.1 Sensor Requirement

- 只使用已有控制传感器；
- 增加电压传感器；
- 增加电流传感器；
- 增加温度传感器；
- 增加高频采样通道；
- 特殊阻抗测量硬件。

## 9.2 Intrusiveness

定义：

- **Passive**：完全利用自然运行数据；
- **Semi-invasive**：利用特定运行区间/开关瞬态；
- **Active**：主动注入信号；
- **Offline**：停机测量。

## 9.3 Computational Cost

分类：

- Very Low；
- Low；
- Medium；
- High；
- Very High。

进一步记录是否可以部署到：

- MCU；
- DSP；
- FPGA；
- industrial PC；
- cloud。

## 9.4 Real-Time Capability

记录：

- sample rate；
- window length；
- execution time；
- memory；
- processor（如有）。

## 9.5 Operating-Point Robustness

是否对以下变化鲁棒：

- voltage；
- load；
- ripple current；
- switching frequency；
- ambient temperature；
- converter mode；
- transient operating condition。

---

# 10. 建立统一方法评价矩阵

创建：

`method_evaluation_matrix.csv`

每篇核心文献一行。

建议字段：

```text
ID
Title
Authors
Year
Journal
DOI
Capacitor_Type
Converter_Topology
Application
Failure_Mode
Degradation_Mechanism
Health_Indicator
Measured_Variables
Additional_Sensors
Sampling_Rate
Method_Category
Algorithm
Online_Offline
Passive_Active
Temperature_Compensation
Operating_Point_Compensation
Fault_Detection
Fault_Severity
SOH
RUL
Uncertainty
Physics_Based
Data_Driven
Physics_Informed
Dataset_Type
Accelerated_Aging
Real_Converter_Test
Number_of_Samples
Evaluation_Metric
Reported_Accuracy
Processor
Real_Time
Computation_Cost
Industrial_Deployability
Main_Advantage
Main_Limitation
Reproducibility
Code_Available
Data_Available
Notes
```

---

# 11. 强制建立“可部署性评分”

可尝试建立一个 Review 自己提出的评分体系，例如：

## Deployability Score (DS)

由下列因素组成：

- S：额外传感器成本；
- C：计算复杂度；
- I：侵入性；
- R：实时能力；
- O：工作点鲁棒性；
- T：温度鲁棒性；
- G：泛化能力；
- V：实验验证等级。

注意：

**初期不要直接设计主观公式。**

首先统计文献实际特征，之后判断：

- 是否采用定性等级；
- 是否采用 radar chart；
- 是否采用 normalized score；
- 是否设计正式数学指标。

如果没有可靠依据，不要人为制造“综合分数”。

---

# 12. Literature Search Strategy

## 12.1 核心数据库

优先：

1. IEEE Xplore
2. Web of Science
3. Scopus
4. ScienceDirect
5. SpringerLink

辅助：

6. Google Scholar
7. Crossref
8. Semantic Scholar

---

## 12.2 时间范围

### 基础文献

允许追溯至经典早期研究。

### 系统检索重点

**2010–2026**

### 前沿重点

**2020–2026**

必须特别检查截至执行日期的：

**2025–2026 最新论文**

---

# 13. Search Queries

至少执行以下组合。

## Query A — Condition Monitoring

```text
("capacitor" OR "electrolytic capacitor" OR "film capacitor")
AND
("condition monitoring" OR "health monitoring")
AND
("power converter" OR "power electronics")
```

## Query B — SOH

```text
capacitor
AND
("state of health" OR SOH)
AND
(power electronics OR converter)
```

## Query C — RUL / Prognostics

```text
capacitor
AND
("remaining useful life" OR RUL OR prognostics)
```

## Query D — Degradation

```text
capacitor
AND
(degradation OR aging OR ageing)
AND
(model OR diagnosis OR prognostics)
```

## Query E — Data Driven

```text
capacitor
AND
("machine learning" OR "deep learning" OR LSTM OR Transformer)
AND
(health OR degradation OR RUL OR fault)
```

## Query F — Physics-Informed

```text
capacitor
AND
("physics-informed" OR "physics guided" OR "hybrid model" OR "grey-box")
AND
(health OR degradation OR prognostics)
```

## Query G — Digital Twin

```text
capacitor
AND
("digital twin")
AND
(health OR aging OR degradation OR prognostics)
```

## Query H — Online Parameter Estimation

```text
capacitor
AND
("online estimation" OR "parameter estimation")
AND
(ESR OR capacitance OR impedance)
```

---

# 14. Inclusion Criteria

原则上纳入：

- peer-reviewed journal；
- 高水平 conference 中有独立方法贡献的论文；
- capacitor health / degradation / diagnosis / prognosis 直接相关；
- 有明确模型、算法或者实验验证；
- 与 power electronics / converter application 相关；
- 可提取关键方法特征。

---

# 15. Exclusion Criteria

原则上排除：

- 仅做普通电容设计而无健康问题；
- 仅做可靠性统计但无诊断/预测方法；
- 只讨论材料制备且无法连接 PHM；
- 无法核实来源；
- 重复发表；
- 单纯教学论文；
- 非同行评议的低可信来源。

**Supercapacitor 与 battery 不作为本文主体。**

但可在“方法学迁移”章节少量引用，例如：

- SOH；
- RUL；
- physics-informed；
- uncertainty；
- transfer learning。

---

# 16. 文献可信度规则

Agent 必须遵循：

1. **禁止虚构参考文献。**
2. DOI 必须能够验证。
3. Title / Authors / Journal / Year / Volume / Pages 尽量与 publisher 数据核对。
4. Google Scholar 仅用于发现，不作为最终唯一验证来源。
5. ResearchGate 仅用于获取线索，不作为核心元数据依据。
6. 同一论文的 conference 和 journal extension 要建立关联。
7. 无法核验的论文标记：

```text
UNVERIFIED
```

不得进入最终核心证据表。

---

# 17. 建议建立项目目录

```text
Capacitor_PHM_Review/
│
├─ README.md
│
├─ TASK.md
│
├─ 00_scope/
│  ├─ research_questions.md
│  ├─ review_of_reviews.md
│  └─ review_gap_matrix.csv
│
├─ 01_search/
│  ├─ search_strategy.md
│  ├─ search_log.csv
│  ├─ inclusion_exclusion.md
│  └─ screening_log.csv
│
├─ 02_literature/
│  ├─ master_literature.csv
│  ├─ core_papers.csv
│  ├─ review_papers.csv
│  └─ references.bib
│
├─ 03_taxonomy/
│  ├─ phm_taxonomy.md
│  ├─ degradation_taxonomy.md
│  ├─ algorithm_taxonomy.md
│  └─ deployability_taxonomy.md
│
├─ 04_analysis/
│  ├─ method_evaluation_matrix.csv
│  ├─ trend_analysis.md
│  ├─ gap_analysis.md
│  └─ future_directions.md
│
├─ 05_figures/
│  ├─ fig01_phm_evolution/
│  ├─ fig02_degradation_chain/
│  ├─ fig03_taxonomy/
│  ├─ fig04_method_map/
│  ├─ fig05_deployability/
│  └─ fig06_future_framework/
│
├─ 06_paper/
│  ├─ outline.md
│  ├─ main.tex
│  ├─ sections/
│  └─ figures/
│
└─ 99_logs/
   ├─ decisions.md
   └─ changelog.md
```

---

# 18. 建议论文核心图

在完成文献数据库后制作，而不是提前凭感觉画图。

## Fig. 1 — Evolution of Capacitor Health Management

展示：

```text
Parameter Monitoring
        →
Condition Monitoring
        →
Fault Diagnosis
        →
SOH Estimation
        →
RUL Prediction
        →
PHM
        →
Predictive Maintenance
```

并加入代表性年份和方法。

---

## Fig. 2 — Physics-to-PHM Chain

```text
Stress
↓
Physical Degradation
↓
Electrical Parameter Drift
↓
Health Indicator
↓
Diagnostic Model
↓
SOH
↓
RUL
↓
Maintenance Decision
```

这是本文最核心的理论总图之一。

---

## Fig. 3 — Multi-dimensional Taxonomy

四维分类：

```text
Physics
×
Health Indicator
×
Algorithm
×
Deployability
```

避免传统的一维算法分类。

---

## Fig. 4 — Five Generations of Capacitor PHM

```text
G1 Direct Measurement
G2 Online Estimation
G3 Degradation & Prognostics
G4 Data-driven PHM
G5 Physics-informed / Hybrid PHM
```

---

## Fig. 5 — Accuracy vs Deployability Map

横轴：

```text
Industrial Deployability
```

纵轴：

```text
Diagnostic / Prognostic Capability
```

将代表性方法绘制在二维空间。

这张图有潜力成为综述的重要贡献。

---

## Fig. 6 — Future Embedded PHM Architecture

建议提出未来实际变换器的结构：

```text
Existing V/I/T Sensors
        ↓
Edge Feature Extraction
        ↓
Physics-based State Estimator
        ↓
Data-driven Residual Model
        ↓
SOH + Uncertainty
        ↓
RUL
        ↓
Converter Controller / Maintenance
```

---

# 19. 论文初步结构

## 1. Introduction

回答：

- 为什么 capacitor 是 reliability-critical component；
- 为什么 condition monitoring 已经不够；
- 已有综述解决了什么；
- 已有综述没有解决什么；
- 为什么需要 PHM 视角。

最后明确本文贡献。

---

## 2. Capacitor Types, Applications, and Failure Physics

### 2.1 Aluminum Electrolytic Capacitors  
### 2.2 Film Capacitors  
### 2.3 Ceramic / Other Capacitors  
### 2.4 Electrical, Thermal, and Environmental Stresses  
### 2.5 Failure Mechanisms and Health Indicators

---

## 3. From Physical Degradation to Health Indicators

### 3.1 ESR  
### 3.2 Capacitance  
### 3.3 Impedance and Dissipation Factor  
### 3.4 Temperature  
### 3.5 Ripple and Transient Features  
### 3.6 Multi-parameter Health Indicators

重点建立：

> **Physical degradation → measurable indicator**

之间的因果关系。

---

## 4. Online Condition Monitoring and Parameter Estimation

### 4.1 Direct Measurement  
### 4.2 Ripple-Based Methods  
### 4.3 Circuit-Model-Based Methods  
### 4.4 Observer and State Estimation  
### 4.5 Signal Injection  
### 4.6 Transient-Based Methods  
### 4.7 Comparative Assessment

---

## 5. SOH Estimation and Degradation Modeling

### 5.1 Empirical Aging Models  
### 5.2 Electro-Thermal Models  
### 5.3 State-Space Degradation Models  
### 5.4 Bayesian / Stochastic Methods  
### 5.5 SOH Definitions and End-of-Life Criteria

这里必须讨论：

> “SOH”在不同论文中定义并不统一。

---

## 6. RUL Prediction and Prognostics

### 6.1 Model-Based Prognostics  
### 6.2 Filtering-Based Prognostics  
### 6.3 Stochastic Degradation Models  
### 6.4 Data-Driven RUL Prediction  
### 6.5 Dynamic Operating Conditions  
### 6.6 Uncertainty Quantification

---

## 7. Data-Driven and Intelligent Capacitor PHM

### 7.1 Conventional Machine Learning  
### 7.2 Deep Learning  
### 7.3 Temporal Models  
### 7.4 Transfer / Domain Adaptation  
### 7.5 Self-Supervised Learning  
### 7.6 Challenges of Dataset Dependence

注意：

不能简单列模型名称。

必须回答：

> AI 方法究竟解决了传统模型的什么问题？

---

## 8. Physics-Informed and Hybrid PHM

作为重点前沿章节。

### 8.1 Physics + Data Fusion  
### 8.2 Grey-Box Models  
### 8.3 Physics-Informed Learning  
### 8.4 Digital Twins  
### 8.5 Uncertainty-Aware PHM  
### 8.6 Opportunities for Capacitor Applications

如果直接针对 capacitor 的论文较少，应明确写成：

> **Emerging research opportunity**

不得夸大现有成熟度。

---

## 9. From Laboratory Algorithms to Embedded Deployment

建议作为本文区别已有综述的核心章节。

### 9.1 Sensor Cost  
### 9.2 Sampling Requirement  
### 9.3 Intrusiveness  
### 9.4 Computational Cost  
### 9.5 Real-Time Implementation  
### 9.6 Robustness to Operating Conditions  
### 9.7 Generalization Across Capacitors  
### 9.8 Industrial Deployment Gap

---

## 10. Benchmarking and Comparative Assessment

建立统一比较表。

重点比较：

```text
Accuracy
Observability
Sensor Requirement
Real-Time Capability
Intrusiveness
Temperature Robustness
Operating-Point Robustness
SOH Capability
RUL Capability
Uncertainty
Computational Cost
Industrial Deployability
```

---

## 11. Open Challenges and Future Research Directions

至少讨论：

### Challenge 1
从单一 ESR/C 参数向 multi-physics health state 转变。

### Challenge 2
动态工作条件下退化与工作点影响难以解耦。

### Challenge 3
温度影响与真实老化影响难以区分。

### Challenge 4
缺少公开标准化 aging dataset。

### Challenge 5
不同型号、不同厂商之间泛化困难。

### Challenge 6
accelerated aging 与正常老化存在 domain gap。

### Challenge 7
SOH 定义与 EOL 标准不统一。

### Challenge 8
RUL prediction 缺少 calibrated uncertainty。

### Challenge 9
AI 模型解释性不足。

### Challenge 10
实验室算法与 MCU/DSP 在线部署之间存在明显鸿沟。

### Challenge 11
Physics-informed / hybrid PHM 尚未充分开发。

### Challenge 12
缺少 converter-level 与 system-level health management。

---

## 12. Conclusion

结论不是再次概述全部方法，而是回答：

> 电容健康监测领域正在从“parameter estimation”向“physics-informed, uncertainty-aware, deployable PHM”演化。

---

# 20. Research Questions

全文至少围绕以下问题展开：

### RQ1
电容的主要失效物理与可观测健康指标之间是什么关系？

### RQ2
现有在线监测方法能够观测到多深层次的健康状态？

### RQ3
哪些方法能够真正估计 SOH，而不是仅估计 ESR / C？

### RQ4
哪些方法能够进行可靠的 RUL prediction？

### RQ5
数据驱动方法相比物理模型真正增加了什么能力？

### RQ6
physics-informed / hybrid 方法是否正在形成新的研究方向？

### RQ7
现有算法距离嵌入式、在线、工业部署还有多远？

### RQ8
未来 capacitor PHM 的关键突破点是什么？

---

# 21. Agent 执行阶段

## Stage 0 — Scope Lock

输出：

```text
00_scope/research_questions.md
00_scope/review_of_reviews.md
00_scope/review_gap_matrix.csv
```

**禁止开始写正式论文。**

---

## Stage 1 — Systematic Search

输出：

```text
01_search/search_strategy.md
01_search/search_log.csv
01_search/screening_log.csv
02_literature/master_literature.csv
02_literature/references.bib
```

---

## Stage 2 — Core Paper Selection

建立：

```text
02_literature/core_papers.csv
```

核心论文必须满足：

- 方法代表性强；
- 来源可靠；
- 信息完整；
- 可用于方法比较。

---

## Stage 3 — Taxonomy Construction

输出：

```text
03_taxonomy/phm_taxonomy.md
03_taxonomy/degradation_taxonomy.md
03_taxonomy/algorithm_taxonomy.md
03_taxonomy/deployability_taxonomy.md
```

---

## Stage 4 — Evidence Matrix

输出：

```text
04_analysis/method_evaluation_matrix.csv
```

这一阶段完成前：

**不要写正文。**

---

## Stage 5 — Gap Analysis

输出：

```text
04_analysis/trend_analysis.md
04_analysis/gap_analysis.md
04_analysis/future_directions.md
```

必须区分：

```text
Evidence-supported gap
```

和：

```text
Author-proposed research opportunity
```

不能混淆。

---

## Stage 6 — Paper Architecture

输出：

```text
06_paper/outline.md
```

要求细化至三级标题，并为每节标注：

- 本节核心论点；
- 使用哪些核心论文；
- 使用哪个表；
- 使用哪个图；
- 本节最终结论。

---

## Stage 7 — Figures First

先制作六张核心图的草稿和数据依据。

禁止制作没有文献数据支撑的“装饰性科研图”。

---

## Stage 8 — Manuscript v0.1

只有 Stage 0–7 完成并审核通过后，才开始：

```text
06_paper/main.tex
```

---

# 22. 文献数量建议

不要机械追求数量。

建议目标：

- Review papers：15–30 篇；
- Core method papers：80–120 篇；
- Extended literature：150–250 篇；
- 最终参考文献：约 150–220 篇。

最终数量由“文献饱和度”决定。

---

# 23. Literature Saturation Stop Condition

当连续新增检索轮次主要出现：

- 已收录论文；
- 同类方法重复；
- 无新算法类别；
- 无新健康指标；
- 无新退化机理；
- 无新 PHM 层级；
- 无新部署模式；

则可认为 taxonomy 基本达到饱和。

但必须额外执行：

```text
2025 latest
2026 latest
early access
online first
```

专项检索，避免漏掉最新研究。

---

# 24. 最重要的写作约束

## 不允许

### 1. 文献流水账

错误：

```text
A proposed...
B proposed...
C proposed...
```

全文不得以这种方式组织。

---

### 2. 只比较 accuracy

一个实验室数据集上的 99% accuracy 不意味着方法更先进。

---

### 3. 把 ESR estimation 等价为 PHM

必须区分：

```text
parameter estimation
≠
health assessment
≠
SOH
≠
RUL
≠
PHM
```

---

### 4. 过度宣传 AI

AI 章节必须讨论：

- data scarcity；
- domain shift；
- explainability；
- uncertainty；
- deployment；
- operating-condition variation。

---

### 5. 编造研究空白

所有“无人研究”“首次”等表述必须经过系统检索。

原则上避免：

```text
No study has...
```

除非有非常强的证据。

推荐：

```text
Relatively limited attention has been paid to...
```

---

# 25. 本综述预期真正贡献

最终论文应力争形成以下 5 个贡献。

## Contribution 1

建立：

> **Physics → Indicator → Diagnosis → SOH → RUL → Maintenance**

统一 PHM 链条。

---

## Contribution 2

提出：

> **Five-generation evolution of capacitor PHM**

从直接参数监测发展到 physics-informed intelligent PHM。

---

## Contribution 3

建立多维 taxonomy：

```text
Capacitor physics
×
Health indicator
×
Algorithm
×
PHM level
×
Deployability
```

---

## Contribution 4

首次或较系统地把：

> **Industrial / Embedded Deployability**

作为 capacitor PHM 方法评价的重要独立维度。

注意：最终是否可以使用“首次”必须经过 review-of-reviews 后决定。

---

## Contribution 5

提出未来：

> **Physics-informed + uncertainty-aware + edge-deployable capacitor PHM**

研究框架。

---

# 26. 最终目标判断

本综述不应成为：

> “又一篇电容 ESR 与电容量检测方法综述”。

而应该成为：

> **一篇解释电容健康管理技术如何从 Condition Monitoring 走向 Prognostics and Health Management 的系统综述。**

核心思想：

```text
Monitor less superficially.
Understand degradation physically.
Estimate health quantitatively.
Predict failure probabilistically.
Deploy PHM practically.
```

---

# 27. Agent 当前立即执行任务

Agent 从 **Stage 0** 开始。

第一轮只完成：

1. 系统检索已有 capacitor review papers；
2. 建立 `review_of_reviews.md`；
3. 建立 `review_gap_matrix.csv`；
4. 判断本文 proposed taxonomy 是否已经被已有综述完整覆盖；
5. 搜索 2024–2026 最新综述和高被引/代表性 PHM 论文；
6. 给出对本文创新定位的：
   - `KEEP`
   - `MODIFY`
   - `REJECT`
   判定；
7. 如果为 `MODIFY`，提出新的差异化综述主线；
8. 不进入正式论文写作。

第一轮最终输出：

```text
STAGE0_REPORT.md
```

报告末尾必须明确回答：

> **Based on the existing review literature, is a new capacitor PHM review scientifically justified, and what is the strongest defensible novelty of the proposed review?**

---

# 28. Stage 0 通过标准

只有同时满足以下条件才进入 Stage 1：

- 已核验主要既有综述；
- 2024–2026 最新综述专项搜索完成；
- review gap matrix 完成；
- 新综述与 2016 / 2020 / 2023 / 2025 代表性综述存在清晰差异；
- 至少形成一个可证据支持的独立 taxonomy；
- deployability 视角确认具有增量价值；
- PHM / SOH / RUL 文献量足以支持独立章节；
- physics-informed / hybrid 部分的成熟度已客观评估；
- 不存在“仅换标题、内容与已有综述高度重复”的问题。

若不满足，则停止进入论文写作，重新定义 scope。

---

**项目建议名称：`Capacitor_PHM_Review`**  
**当前任务：只执行 Stage 0，先证明这篇综述值得写，再开始写。**
