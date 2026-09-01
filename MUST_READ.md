# 必读清单 — 只有这些需要全文

**机读版：** [02_literature/must_read.csv](02_literature/must_read.csv)

---

## 先说清楚：引用不需要 PDF

参考文献条目需要的是**标题 / 作者 / 期刊 / 卷期页 / 年份 / DOI**——这些我已经全部通过 Crossref 逐条核验，覆盖 805 篇文献。最终参考文献表要列 150–220 篇，**一篇 PDF 都不用再下**。

**需要全文的只有一种情况：要从正文里抠数据。** 证据矩阵（`method_evaluation_matrix.csv`）里的采样率、处理器、执行时间、内存、验证条件、报告精度——这些字段摘要里没有，只能读正文。这恰恰是创新点 C（可部署性轴）的证据来源。

所以清单从 129 篇砍到 **56 篇**。

---

## 一个值得说明的发现

我自动下载的 82 篇里，**只有 3 篇属于共引≥4 的正典**。开放获取和经典地位几乎不相关——领域里那些老的 IEEE 经典论文全在付费墙后，而 OA 能拿到的多是边缘文献。所以那 82 篇不能替代下面这份清单。

---

## T1 — L5+ 预测性论文　（17 篇）

**不可省略。** 第 5–6 合并章的全部证据基础，也是「L5 为空」这个核心论断的直接检验对象。若只下一组，下这组。

### IEEE Xplore（10 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| **L7** | 2 | `10.1109/tie.2016.2586020` | Lifetime Monitoring of Electrolytic Capacitor to Maximize Earnings From Grid-Feeding P | IEEE Transactions on Industrial  2016 |
| **L6** | 6 | `10.1109/tia.2010.2049972` | A Real-Time Predictive-Maintenance System of Aluminum Electrolytic Capacitors Used in  | IEEE Transactions on Industry Ap 2010 |
| **L6** | 4 | `10.1109/tia.2005.858258` | Life Prediction Modeling of Bus Capacitors in AC Variable-Frequency Drives | IEEE Transactions on Industry Ap 2005 |
| **L6** | 3 | `10.1109/tpel.2018.2865710` | Mission Profile Based Reliability Evaluation of Capacitor Banks in Wind Power Converte | IEEE Transactions on Power Elect 2019 |
| **L6** | 2 | `10.1109/tie.2016.2581156` | PoF-Simulation-Assisted Reliability Prediction for Electrolytic Capacitor in LED Drive | IEEE Transactions on Industrial  2016 |
| **L6** | 1 | `10.1109/tpel.2014.2360662` | Computationally Efficient, Real-Time, and Embeddable Prognostic Techniques for Power E | IEEE Transactions on Power Elect 2015 |
| **L6** | 1 | `10.1109/ias.1996.559241` | Life prediction model for aluminum electrolytic capacitors | IAS '96. Conference Record of th  |
| **L6** | 1 | `10.1109/apec.2010.5433384` | A life prediction scheme for electrolytic capacitors in power converters without curre | 2010 Twenty-Fifth Annual IEEE Ap 2010 |
| **L6** | 1 | `10.1109/tps.2013.2243476` | Lifetime Prediction of Metallized Film Capacitors Based on Capacitance Loss | IEEE Transactions on Plasma Scie 2013 |
| **L6** | 1 | `10.1109/tdmr.2011.2162517` | Prognostics of Multilayer Ceramic Capacitors Via the Parameter Residuals | IEEE Transactions on Device and  2012 |

### Elsevier / other（6 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| **L7** | 1 | `10.1109/phm.2011.5939474` | Degradation model and maintenance strategy of the electrolytic capacitors for electron | 2011 Prognostics and System Heal 2011 |
| **L6** | 2 | `10.1177/1687814018781170` | An intelligent prognostic model for electrolytic capacitors health monitoring: A desig | Advances in Mechanical Engineeri 2018 |
| **L6** | 1 | `10.1016/j.microrel.2018.05.020` | Adaptive and robust prediction for the remaining useful life of electrolytic capacitor | Microelectronics Reliability 2018 |
| **L6** | 1 | `10.1016/j.microrel.2023.114928` | A remaining useful life prediction method of aluminum electrolytic capacitor based on  | Microelectronics Reliability 2023 |
| **L6** | 1 | `10.2514/6.2011-1519` | Towards Prognostics of Electrolytic Capacitors | Infotech@Aerospace 2011 2011 |
| **L6** | 1 | `10.1109/med48518.2020.9182829` | Zonotopic Extended Kalman Filter For RUL Forecasting With Unknown Degradation Behavior | 2020 28th Mediterranean Conferen 2020 |

### IET（1 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| **L6** | 1 | `10.1049/iet-pel.2015.0636` | Fractional order equivalent series resistance modelling of electrolytic capacitor and  | IET Power Electronics 2016 |

## T2 — 诊断/严重度层的正典　（6 篇）

能力阶梯 L3/L4 两级的代表作，都被 ≥4 篇独立综述共引。

### IEEE Xplore（6 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| L4 | 4 | `10.1109/tie.2018.2880725` | Health Estimation of Individual Capacitors in a Bank With Reduced Sensor Requirements | IEEE Transactions on Industrial  2019 |
| L3 | 6 | `10.1109/63.261004` | Use of ESR for deterioration diagnosis of electrolytic capacitor | IEEE Transactions on Power Elect 1993 |
| L3 | 6 | `10.1109/2943.974353` | Realization of a Smart: Electrolytic Capacitor Circuit: Electrolytic Capacitor Circuit | IEEE Industry Applications Magaz 2002 |
| L3 | 5 | `10.1109/tie.2012.2218561` | Fault Diagnosis of DC-Link Capacitors in Three-Phase AC/DC PWM Converters by Online Es | IEEE Transactions on Industrial  2013 |
| L3 | 4 | `10.1109/63.728347` | Failure prediction of electrolytic capacitors during operation of a switchmode power s | IEEE Transactions on Power Elect 1998 |
| L3 | 4 | `10.1109/tie.2007.903975` | Online Failure Prediction of the Electrolytic Capacitor for LC Filter of Switching-Mod | IEEE Transactions on Industrial  2008 |

## T3 — 参数估计层的正典　（33 篇）

第 4 章与方法比较表的主体。可部署性字段（传感器需求/采样率/处理器）主要从这批论文的正文里抠。

### IEEE Xplore（30 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| L2 | 6 | `10.1109/tia.2012.2222333` | Condition Monitoring of DC-Link Capacitors in Aerospace Drives | IEEE Transactions on Industry Ap 2012 |
| L2 | 5 | `10.1109/tpel.2010.2059713` | Life-Cycle Monitoring and Voltage-Managing Unit for DC-Link Electrolytic Capacitors in | IEEE Transactions on Power Elect 2011 |
| L2 | 5 | `10.1109/tie.2009.2022077` | A Simple Offline Technique for Evaluating the Condition of Aluminum–Electrolytic–Capac | IEEE Transactions on Industrial  2009 |
| L2 | 5 | `10.1109/tpel.2017.2736162` | Quasi-Online Technique for Health Monitoring of Capacitor in Single-Phase Solar Invert | IEEE Transactions on Power Elect 2018 |
| L2 | 5 | `10.1109/pesc.2005.1582040` | A Real Time Method to Estimate Electrolytic Capacitor Condition in PWM Adjustable Spee | IEEE 36th Conference on Power El  |
| L2 | 5 | `10.1109/tim.2008.925013` | An Economic Offline Technique for Estimating the Equivalent Circuit of Aluminum Electr | IEEE Transactions on Instrumenta 2008 |
| L2 | 4 | `10.1109/tpel.2014.2339374` | Deterioration Monitoring of DC-Link Capacitors in AC Machine Drives by Current Injecti | IEEE Transactions on Power Elect 2015 |
| L2 | 4 | `10.1109/tim.2009.2032960` | An Online and Noninvasive Technique for the Condition Monitoring of Capacitors in Boos | IEEE Transactions on Instrumenta 2010 |
| L2 | 4 | `10.1109/tpel.2014.2383436` | A Current-Sensorless Online ESR and C Identification Method for Output Capacitor of Bu | IEEE Transactions on Power Elect 2015 |
| L2 | 4 | `10.1109/tia.2008.2002181` | DC-Link Capacitance Estimation in AC/DC/AC PWM Converters Using Voltage Injection | IEEE Transactions on Industry Ap 2008 |
| L2 | 4 | `10.1109/tie.2018.2835393` | A VEN Condition Monitoring Method of DC-Link Capacitors for Power Converters | IEEE Transactions on Industrial  2019 |
| L2 | 4 | `10.1109/tia.2018.2845889` | Online Condition Monitoring System for DC-Link Capacitor in Industrial Power Converter | IEEE Transactions on Industry Ap 2018 |
| L2 | 4 | `10.1109/tpel.2019.2951859` | Condition Monitoring of DC-Link Capacitors Using Goertzel Algorithm for Failure Precur | IEEE Transactions on Power Elect 2020 |
| L2 | 4 | `10.1109/tpel.2018.2890617` | An Online ESR Estimation Method for Output Capacitor of Boost Converter | IEEE Transactions on Power Elect 2019 |
| L2 | 4 | `10.1109/tpel.2018.2857832` | Reference Submodule Based Capacitor Monitoring Strategy for Modular Multilevel Convert | IEEE Transactions on Power Elect 2019 |
| L2 | 4 | `10.1109/apex.2007.357646` | Real-Time Condition Monitoring of the Electrolytic Capacitors for Power Electronics Ap | APEC 07 - Twenty-Second Annual I 2007 |
| L2 | 4 | `10.1109/ecce.2014.6953683` | Condition monitoring of submodule capacitors in modular multilevel converters | 2014 IEEE Energy Conversion Cong 2014 |
| L2 | 4 | `10.1109/tpel.2017.2762341` | Noninvasive Technique for DC-Link Capacitance Estimation in Single-Phase Inverters | IEEE Transactions on Power Elect 2018 |
| L2 | 4 | `10.1109/tpel.2019.2917937` | Condition Monitoring for Submodule Capacitors in Modular Multilevel Converters | IEEE Transactions on Power Elect 2019 |
| L2 | 4 | `10.1109/tpel.2019.2956808` | Capacitor Condition Monitoring Based on the DC-Side Start-Up of Modular Multilevel Con | IEEE Transactions on Power Elect 2020 |
| L2 | 4 | `10.1109/tim.2009.2019719` | Condition Monitoring of Metallized Polypropylene Film Capacitors in Railway Power Trai | IEEE Transactions on Instrumenta 2009 |
| L2 | 4 | `10.1109/tim.2017.2749838` | Noninvasive Online Condition Monitoring of Output Capacitor’s ESR and C for a Flyback  | IEEE Transactions on Instrumenta 2017 |
| L2 | 4 | `10.1109/isie.2007.4374704` | Using Newton-Raphson Method to Estimate the Condition of Aluminum Electrolytic Capacit | 2007 IEEE International Symposiu 2007 |
| L2 | 4 | `10.1109/jsen.2019.2945943` | Online Monitoring of Aluminum Electrolytic Capacitors in Photovoltaic Systems by Magne | IEEE Sensors Journal 2020 |
| L2 | 4 | `10.1109/jsen.2019.2929537` | Condition Monitoring of Electrolytic Capacitors in Boost Converters by Magnetic Sensor | IEEE Sensors Journal 2019 |
| L2 | 4 | `10.1109/iecon.2008.4758011` | An automatic technique to obtain the equivalent circuit of aluminum electrolytic capac | 2008 34th Annual Conference of I 2008 |
| L2 | 4 | `10.1109/demped.2009.5292791` | Using input current and output voltage ripple to estimate the output filter condition  | 2009 IEEE International Symposiu 2009 |
| L0 | 4 | `10.1109/tia.2002.802922` | The service life of large aluminum electrolytic capacitors: effects of construction an | IEEE Transactions on Industry Ap 2002 |
| n/a | 4 | `10.1109/tia.2011.2124436` | An Industry-Based Survey of Reliability in Power Electronic Converters | IEEE Transactions on Industry Ap 2011 |
| n/a | 4 | `10.1109/tvt.2012.2206082` | Analysis and Evaluation of DC-Link Capacitors for High-Power-Density Electric Vehicle  | IEEE Transactions on Vehicular T 2012 |

### IET（3 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 |
|---|---:|---|---|---|
| L2 | 4 | `10.1049/ip-epa:20050027` | Online capacitance estimation of DC-link electrolytic capacitors for three-phase AC/DC | IEE Proceedings - Electric Power 2005 |
| L2 | 4 | `10.1049/iet-pel.2016.0603` | Capacitor impedance estimation utilizing dc‐link voltage oscillations in single phase  | IET Power Electronics 2017 |
| L2 | 4 | `10.1049/iet-pel.2018.5394` | Online estimation scheme of output capacitor's ESR and tan
                    δ
      | IET Power Electronics 2019 |

---

## 归档

- T1 → `ReferencePaper/04_SOH_RUL_Prognostics/`
- T2、T3 → `ReferencePaper/03_CM_ParameterEstimation/`

文件名随意，我按内容识别。

## 如果还嫌多

**只下 T1 的 17 篇也能推进。** 那是核心论断的检验，也是新章节的全部素材。T2/T3 缺席的后果是方法比较表和可部署性轴要延后到下一批——论文照样能开写，只是第 4 章和第 9 章要留白。
