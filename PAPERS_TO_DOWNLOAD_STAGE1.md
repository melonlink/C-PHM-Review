# 需要您下载的论文 — Stage 1

**机读版本：** [02_literature/papers_to_obtain_stage1.csv](02_literature/papers_to_obtain_stage1.csv)
**能力分级证据表：** [04_analysis/stage1_capability_matrix.csv](04_analysis/stage1_capability_matrix.csv)

---

## 这份清单怎么来的

OpenAlex 被 IP 级限流，Crossref 相关度检索召回率仅 50%（两次尝试均已否决，见 [search_strategy.md](01_search/search_strategy.md) §3）。改用**共被引普查**：
把手上 10 篇综述在 Crossref 登记的参考文献全部取出 → **619 篇唯一文献**，按「被多少篇*独立*综述共同引用」排序。这个信号不依赖任何相关度排序函数，完全可复现。

其中 240 篇（共引≥2 的 127 篇 + 单引但标题含 PHM 高阶词的 113 篇）交由 **30 个智能体做 PHM 能力分级 + 对抗性审计**，判定出 **151 篇电容相关**论文，另 89 篇为半导体/PCB/电池等（来自 Fassi 2024 的跨器件参考文献），已剔除。

Unpaywall 确认 OA 后我已自动下载 **65 篇**，库存 12 → **82 篇**。下面是剩下需要您用机构权限获取的。

---

## A 组 — 经审计确认的**真正预测性论文**（L6 RUL / L7 维护决策）　（16 篇）

**最高优先级。** 全语料 151 篇里只有 17 篇达到 L5+，是第 5、6 章能否成立的全部证据。每一篇的等级都经过两个独立视角的对抗性审计。

### IEEE Xplore（9 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| **L7** | 2 | `10.1109/tie.2016.2586020` | Lifetime Monitoring of Electrolytic Capacitor to Maximize Earnings From Grid-Feeding PV  | IEEE Transactions on Industrial El 2016 | `04_SOH_RUL_Prognostics` |
| **L6** | 6 | `10.1109/tia.2010.2049972` | A Real-Time Predictive-Maintenance System of Aluminum Electrolytic Capacitors Used in Un | IEEE Transactions on Industry Appl 2010 | `04_SOH_RUL_Prognostics` |
| **L6** | 4 | `10.1109/tia.2005.858258` | Life Prediction Modeling of Bus Capacitors in AC Variable-Frequency Drives | IEEE Transactions on Industry Appl 2005 | `04_SOH_RUL_Prognostics` |
| **L6** | 2 | `10.1109/tie.2016.2581156` | PoF-Simulation-Assisted Reliability Prediction for Electrolytic Capacitor in LED Drivers | IEEE Transactions on Industrial El 2016 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/tpel.2014.2360662` | Computationally Efficient, Real-Time, and Embeddable Prognostic Techniques for Power Ele | IEEE Transactions on Power Electro 2015 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/ias.1996.559241` | Life prediction model for aluminum electrolytic capacitors | IAS '96. Conference Record of the   | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/apec.2010.5433384` | A life prediction scheme for electrolytic capacitors in power converters without current | 2010 Twenty-Fifth Annual IEEE Appl 2010 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/tps.2013.2243476` | Lifetime Prediction of Metallized Film Capacitors Based on Capacitance Loss | IEEE Transactions on Plasma Scienc 2013 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/tdmr.2011.2162517` | Prognostics of Multilayer Ceramic Capacitors Via the Parameter Residuals | IEEE Transactions on Device and Ma 2012 | `04_SOH_RUL_Prognostics` |

### Other（4 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| **L7** | 1 | `10.1109/phm.2011.5939474` | Degradation model and maintenance strategy of the electrolytic capacitors for electronic | 2011 Prognostics and System Health 2011 | `04_SOH_RUL_Prognostics` |
| **L6** | 2 | `10.1177/1687814018781170` | An intelligent prognostic model for electrolytic capacitors health monitoring: A design  | Advances in Mechanical Engineering 2018 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.2514/6.2011-1519` | Towards Prognostics of Electrolytic Capacitors | Infotech@Aerospace 2011 2011 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1109/med48518.2020.9182829` | Zonotopic Extended Kalman Filter For RUL Forecasting With Unknown Degradation Behaviors | 2020 28th Mediterranean Conference 2020 | `04_SOH_RUL_Prognostics` |

### Elsevier（2 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| **L6** | 1 | `10.1016/j.microrel.2018.05.020` | Adaptive and robust prediction for the remaining useful life of electrolytic capacitors | Microelectronics Reliability 2018 | `04_SOH_RUL_Prognostics` |
| **L6** | 1 | `10.1016/j.microrel.2023.114928` | A remaining useful life prediction method of aluminum electrolytic capacitor based on wi | Microelectronics Reliability 2023 | `04_SOH_RUL_Prognostics` |

### IET（1 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| **L6** | 1 | `10.1049/iet-pel.2015.0636` | Fractional order equivalent series resistance modelling of electrolytic capacitor and fr | IET Power Electronics 2016 | `04_SOH_RUL_Prognostics` |

## B 组 — 领域正典（被 ≥4 篇独立综述共引）　（37 篇）

方法学骨干，第 4 章与基准比较表的主体。

### IEEE Xplore（34 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L4 | 4 | `10.1109/tie.2018.2880725` | Health Estimation of Individual Capacitors in a Bank With Reduced Sensor Requirements | IEEE Transactions on Industrial El 2019 | `03_CM_ParameterEstimation` |
| L3 | 6 | `10.1109/63.261004` | Use of ESR for deterioration diagnosis of electrolytic capacitor | IEEE Transactions on Power Electro 1993 | `03_CM_ParameterEstimation` |
| L3 | 6 | `10.1109/2943.974353` | Realization of a Smart: Electrolytic Capacitor Circuit: Electrolytic Capacitor Circuits  | IEEE Industry Applications Magazin 2002 | `03_CM_ParameterEstimation` |
| L3 | 5 | `10.1109/tie.2012.2218561` | Fault Diagnosis of DC-Link Capacitors in Three-Phase AC/DC PWM Converters by Online Esti | IEEE Transactions on Industrial El 2013 | `03_CM_ParameterEstimation` |
| L3 | 4 | `10.1109/63.728347` | Failure prediction of electrolytic capacitors during operation of a switchmode power sup | IEEE Transactions on Power Electro 1998 | `03_CM_ParameterEstimation` |
| L3 | 4 | `10.1109/tie.2007.903975` | Online Failure Prediction of the Electrolytic Capacitor for LC Filter of Switching-Mode  | IEEE Transactions on Industrial El 2008 | `03_CM_ParameterEstimation` |
| L2 | 6 | `10.1109/tia.2012.2222333` | Condition Monitoring of DC-Link Capacitors in Aerospace Drives | IEEE Transactions on Industry Appl 2012 | `03_CM_ParameterEstimation` |
| L2 | 5 | `10.1109/tpel.2010.2059713` | Life-Cycle Monitoring and Voltage-Managing Unit for DC-Link Electrolytic Capacitors in P | IEEE Transactions on Power Electro 2011 | `06_PhysicsInformed_DigitalTwin` |
| L2 | 5 | `10.1109/tie.2009.2022077` | A Simple Offline Technique for Evaluating the Condition of Aluminum–Electrolytic–Capacit | IEEE Transactions on Industrial El 2009 | `03_CM_ParameterEstimation` |
| L2 | 5 | `10.1109/tpel.2017.2736162` | Quasi-Online Technique for Health Monitoring of Capacitor in Single-Phase Solar Inverter | IEEE Transactions on Power Electro 2018 | `03_CM_ParameterEstimation` |
| L2 | 5 | `10.1109/pesc.2005.1582040` | A Real Time Method to Estimate Electrolytic Capacitor Condition in PWM Adjustable Speed  | IEEE 36th Conference on Power Elec  | `03_CM_ParameterEstimation` |
| L2 | 5 | `10.1109/tim.2008.925013` | An Economic Offline Technique for Estimating the Equivalent Circuit of Aluminum Electrol | IEEE Transactions on Instrumentati 2008 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2014.2339374` | Deterioration Monitoring of DC-Link Capacitors in AC Machine Drives by Current Injection | IEEE Transactions on Power Electro 2015 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tim.2009.2032960` | An Online and Noninvasive Technique for the Condition Monitoring of Capacitors in Boost  | IEEE Transactions on Instrumentati 2010 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2014.2383436` | A Current-Sensorless Online ESR and C Identification Method for Output Capacitor of Buck | IEEE Transactions on Power Electro 2015 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tia.2008.2002181` | DC-Link Capacitance Estimation in AC/DC/AC PWM Converters Using Voltage Injection | IEEE Transactions on Industry Appl 2008 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tie.2018.2835393` | A VEN Condition Monitoring Method of DC-Link Capacitors for Power Converters | IEEE Transactions on Industrial El 2019 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2019.2951859` | Condition Monitoring of DC-Link Capacitors Using Goertzel Algorithm for Failure Precurso | IEEE Transactions on Power Electro 2020 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2018.2890617` | An Online ESR Estimation Method for Output Capacitor of Boost Converter | IEEE Transactions on Power Electro 2019 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2018.2857832` | Reference Submodule Based Capacitor Monitoring Strategy for Modular Multilevel Converter | IEEE Transactions on Power Electro 2019 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/apex.2007.357646` | Real-Time Condition Monitoring of the Electrolytic Capacitors for Power Electronics Appl | APEC 07 - Twenty-Second Annual IEE 2007 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/ecce.2014.6953683` | Condition monitoring of submodule capacitors in modular multilevel converters | 2014 IEEE Energy Conversion Congre 2014 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2017.2762341` | Noninvasive Technique for DC-Link Capacitance Estimation in Single-Phase Inverters | IEEE Transactions on Power Electro 2018 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tpel.2019.2917937` | Condition Monitoring for Submodule Capacitors in Modular Multilevel Converters | IEEE Transactions on Power Electro 2019 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tim.2009.2019719` | Condition Monitoring of Metallized Polypropylene Film Capacitors in Railway Power Trains | IEEE Transactions on Instrumentati 2009 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/tim.2017.2749838` | Noninvasive Online Condition Monitoring of Output Capacitor’s ESR and C for a Flyback Co | IEEE Transactions on Instrumentati 2017 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/isie.2007.4374704` | Using Newton-Raphson Method to Estimate the Condition of Aluminum Electrolytic Capacitor | 2007 IEEE International Symposium  2007 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/jsen.2019.2945943` | Online Monitoring of Aluminum Electrolytic Capacitors in Photovoltaic Systems by Magneto | IEEE Sensors Journal 2020 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/jsen.2019.2929537` | Condition Monitoring of Electrolytic Capacitors in Boost Converters by Magnetic Sensors | IEEE Sensors Journal 2019 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/iecon.2008.4758011` | An automatic technique to obtain the equivalent circuit of aluminum electrolytic capacit | 2008 34th Annual Conference of IEE 2008 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1109/demped.2009.5292791` | Using input current and output voltage ripple to estimate the output filter condition of | 2009 IEEE International Symposium  2009 | `03_CM_ParameterEstimation` |
| L0 | 4 | `10.1109/tia.2002.802922` | The service life of large aluminum electrolytic capacitors: effects of construction and  | IEEE Transactions on Industry Appl 2002 | `02_Failure_Physics` |
| n/a | 4 | `10.1109/tia.2011.2124436` | An Industry-Based Survey of Reliability in Power Electronic Converters | IEEE Transactions on Industry Appl 2011 | `00_Reviews_Capacitor` |
| n/a | 4 | `10.1109/tvt.2012.2206082` | Analysis and Evaluation of DC-Link Capacitors for High-Power-Density Electric Vehicle Dr | IEEE Transactions on Vehicular Tec 2012 | `02_Failure_Physics` |

### IET（3 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L2 | 4 | `10.1049/ip-epa:20050027` | Online capacitance estimation of DC-link electrolytic capacitors for three-phase AC/DC/A | IEE Proceedings - Electric Power A 2005 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1049/iet-pel.2016.0603` | Capacitor impedance estimation utilizing dc‐link voltage oscillations in single phase in | IET Power Electronics 2017 | `03_CM_ParameterEstimation` |
| L2 | 4 | `10.1049/iet-pel.2018.5394` | Online estimation scheme of output capacitor's ESR and tan
                    δ
        | IET Power Electronics 2019 | `03_CM_ParameterEstimation` |

## C 组 — 核心文献（被 ≥2 篇综述共引）　（61 篇）

补齐方法覆盖面。

### IEEE Xplore（47 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L3 | 3 | `10.1109/tie.2017.2674598` | Low-Frequency Impedance Monitoring and Corresponding Failure Criteria for Aluminum Elect | IEEE Transactions on Industrial El 2017 | `03_CM_ParameterEstimation` |
| L3 | 3 | `10.1109/ccece.2015.7129353` | Capacitor aging detection for the DC filters in the power electronic converters using AN | 2015 IEEE 28th Canadian Conference 2015 | `05_DataDriven_AI` |
| L3 | 3 | `10.1109/isie.2004.1572002` | Use of ESR to predict failure of output filtering capacitors in boost converters | 2004 IEEE International Symposium  2004 | `03_CM_ParameterEstimation` |
| L3 | 3 | `10.1109/pesc.2008.4592252` | A non-invasive technique for fault diagnosis of SMPS | 2008 IEEE Power Electronics Specia 2008 | `03_CM_ParameterEstimation` |
| L3 | 2 | `10.1109/tpel.2021.3135873` | Condition Monitoring of DC-Link Capacitors Using Time–Frequency Analysis and Machine Lea | IEEE Transactions on Power Electro 2022 | `05_DataDriven_AI` |
| L3 | 2 | `10.1109/apec.2005.1453106` | Failure prediction of electrolytic capacitor using DSP methods | Twentieth Annual IEEE Applied Powe  | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/tpel.2015.2496267` | An Online Monitoring Scheme of DC-Link Capacitor's ESR and C for a Boost PFC Converter | IEEE Transactions on Power Electro 2016 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/tie.2016.2582470` | Online Monitoring Technique for Aluminum Electrolytic Capacitor in Solar PV-Based DC Sys | IEEE Transactions on Industrial El 2016 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/tpel.2019.2904551` | High-Accuracy Capacitance Monitoring of DC-Link Capacitor in VSI Systems by
             | IEEE Transactions on Power Electro 2019 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/powereng.2015.7266382` | Condition monitoring for DC-link capacitors based on artificial neural network algorithm | 2015 IEEE 5th International Confer 2015 | `05_DataDriven_AI` |
| L2 | 3 | `10.1109/tim.2009.2038018` | Simple Experimental Techniques to Characterize Capacitors in a Wide Range of Frequencies | IEEE Transactions on Instrumentati 2010 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/tpel.2018.2868564` | A Noninvasive Online Monitoring Method of Output Capacitor's C and ESR for DCM Flyback C | IEEE Transactions on Power Electro 2019 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/ifeec.2017.7992442` | Artificial Neural Network based DC-link capacitance estimation in a diode-bridge front-e | 2017 IEEE 3rd International Future 2017 | `05_DataDriven_AI` |
| L2 | 3 | `10.1109/imtc.2006.328273` | An Experimental Technique for Estimating the ESR and Reactance Intrinsic Values of Alumi | 2006 IEEE Instrumentation and Meas 2006 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/isie.2010.5637333` | Estimating aluminum electrolytic capacitors condition using a low frequency transformer  | 2010 IEEE International Symposium  2010 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/vppc.2012.6422642` | Condition monitoring of DC-link capacitors in drive system for electric vehicles | 2012 IEEE Vehicle Power and Propul 2012 | `03_CM_ParameterEstimation` |
| L2 | 3 | `10.1109/icit.2005.1600615` | An Experimental Technique for Estimating the Aluminum Electrolytic Capacitor Equivalent  | 2005 IEEE International Conference  | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tia.2008.2002220` | Condition Monitoring of DC-Link Electrolytic Capacitors in Adjustable-Speed Drives | IEEE Transactions on Industry Appl 2008 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2016.2552039` | Application of an Efficient Rogowski Coil Sensor for Switch Fault Diagnosis and Capacito | IEEE Transactions on Power Electro 2017 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2015.2472459` | Low Sampling Rate Online Parameters Monitoring of DC–DC Converters for Predictive-Mainte | IEEE Transactions on Power Electro 2016 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tie.2017.2652372` | Online Condition Monitoring for Both IGBT Module and DC-Link Capacitor of Power Converte | IEEE Transactions on Industrial El 2017 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tie.2019.2912771` | Failure Prediction of Submodule Capacitors in Modular Multilevel Converter by Monitoring | IEEE Transactions on Industrial El 2020 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tia.2018.2836923` | Online Estimation of Aluminum Electrolytic-Capacitor Parameters Using a Modified Prony's | IEEE Transactions on Industry Appl 2018 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2019.2957027` | Online Estimation of ESR for DC-Link Capacitor of Boost PFC Converter Using Wavelet Tran | IEEE Transactions on Power Electro 2020 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/ecce.2017.8096961` | Capacitance estimation algorithm based on DC-link voltage harmonics using artificial neu | 2017 IEEE Energy Conversion Congre 2017 | `05_DataDriven_AI` |
| L2 | 2 | `10.1109/tie.2021.3055164` | ESR Estimation for Aluminum Electrolytic Capacitor of Power Electronic Converter Based o | IEEE Transactions on Industrial El 2022 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2010.2062200` | A New Strategy for Condition Monitoring of Adjustable Speed Induction Machine Drive Syst | IEEE Transactions on Power Electro 2011 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2019.2959074` | Online Capacitance Estimation of Submodule Capacitors for Modular Multilevel Converter W | IEEE Transactions on Power Electro 2020 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/pesc.2005.1581687` | Condition Monitoring of Electrolytic Capacitor in Power Electronic Circuits using Adapti | IEEE 36th Conference on Power Elec  | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpel.2021.3121813` | Aging Condition Monitoring for Aluminum Electrolytic Capacitor in Variable Speed Drives | IEEE Transactions on Power Electro 2022 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/ipemc.2016.7512885` | Capacitance estimation for dc-link capacitors in a back-to-back converter based on Artif | 2016 IEEE 8th International Power  2016 | `05_DataDriven_AI` |
| L2 | 2 | `10.1109/tpel.2021.3118602` | Condition Health Monitoring of Modular Multilevel Converter Submodule Capacitors | IEEE Transactions on Power Electro 2022 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/iecon.2009.5414963` | State condition estimation of aluminum electrolytic capacitors used on the primary side  | 2009 35th Annual Conference of IEE 2009 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/pesc.2005.1582038` | Parameter Identification of Power Electronic Circuits Based on Hybrid Model | IEEE 36th Conference on Power Elec  | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tcsii.2020.3040428` | Switching Signals Based Condition Monitoring for Submodule Capacitors in Modular Multile | IEEE Transactions on Circuits and  2021 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/ipemc-ecceasia48364.2020.9367704` | Online Monitoring for Sub-module Capacitance in Modular Multilevel Converter with Four S | 2020 IEEE 9th International Power  2020 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/tpwrd.2022.3176001` | A Hierarchic Capacitor Condition Monitoring Strategy for High-Voltage Modular Multilevel | IEEE Transactions on Power Deliver 2022 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/icit.2015.7125215` | An online technique for condition monitoring of capacitor in PV system | 2015 IEEE International Conference 2015 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/iecon.2017.8216161` | Capacitor monitoring for modular multilevel converters | IECON 2017 - 43rd Annual Conferenc 2017 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/iecon.2005.1569015` | LMS based condition monitoring of electrolytic capacitor | 31st Annual Conference of IEEE Ind 2005 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/ecce.2014.6953873` | A novel online ESR and C identification method for output capacitor of buck converter | 2014 IEEE Energy Conversion Congre 2014 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/iecon.2019.8927539` | Capacitor Monitoring for Full-Bridge Submodule Based Modular Multilevel Converters | IECON 2019 - 45th Annual Conferenc 2019 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/ias.2007.346` | ESR Estimation Method for DC/DC Converters Through Simplified Regression Models | 2007 IEEE Industry Applications An 2007 | `03_CM_ParameterEstimation` |
| L0 | 3 | `10.1109/tdmr.2006.876612` | Linking Corrosion and Catastrophic Failure in Low-Power Metallized Polypropylene Capacit | IEEE Transactions on Device and Ma 2006 | `02_Failure_Physics` |
| L0 | 2 | `10.1109/tpmp.1965.1135396` | The Chemistry of Failure of Aluminum Electrolytic Capacitors | IEEE Transactions on Parts, Materi 1965 | `02_Failure_Physics` |
| n/a | 2 | `10.1109/mei.2010.5383924` | Historical introduction to capacitor technology | IEEE Electrical Insulation Magazin 2010 | `00_Reviews_Capacitor` |
| n/a | 2 | `10.1109/tste.2014.2347967` | Performance Evaluation of Three-Phase Grid-Connected Photovoltaic Inverters Using Electr | IEEE Transactions on Sustainable E 2014 | `00_Reviews_Capacitor` |

### Elsevier（4 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L4 | 2 | `10.1002/(sici)1099-1638(199601)12:1<43::aid-qre981>3.0.co;2-o` | NON-DESTRUCTIVE DETECTION AND LOCALIZATION OF DEFECTS IN MULTILAYER CERAMIC CHIP CAPACIT | Quality and Reliability Engineerin 1996 | `03_CM_ParameterEstimation` |
| L3 | 2 | `10.1016/j.microrel.2016.07.110` | Detection of cracks in multilayer ceramic capacitors by X-ray imaging | Microelectronics Reliability 2016 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/imccc.2012.199` | Fault Diagnosis and Life Prediction of DC-link Aluminum Electrolytic Capacitors Used in  | 2012 Second International Conferen 2012 | `06_PhysicsInformed_DigitalTwin` |
| L0 | 2 | `10.1016/j.microrel.2020.113737` | A method to extract lumped thermal networks of capacitors for reliability oriented desig | Microelectronics Reliability 2020 | `02_Failure_Physics` |

### Other（4 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L2 | 2 | `10.1109/ectc.1998.678924` | A new technique for high frequency characterization of capacitors | 1998 Proceedings. 48th Electronic   | `00_Reviews_Capacitor` |
| L2 | 2 | `10.1109/powereng.2009.4915158` | Using a sinosoidal PWM to estimate the ESR of Aluminum electrolytic capacitors | 2009 International Conference on P 2009 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/phm-chongqing.2018.00143` | Online Output Capacitor Monitor for Buck DC-DC Converter | 2018 Prognostics and System Health 2018 | `03_CM_ParameterEstimation` |
| n/a | 2 | `10.1007/s00202-004-0265-z` | Simple model of an electrolytic capacitor taking into account the temperature and aging  | Electrical Engineering 2006 | `02_Failure_Physics` |

### IET（3 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L3 | 3 | `10.1049/iet-pel.2011.0163` | On-line fault detection of aluminium electrolytic capacitors, in step-down DC–DC convert | IET Power Electronics 2012 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1049/cp.2016.0369` | A New Scheme for Monitoring Submodule Capacitance in Modular Multilevel Converter | 8th IET International Conference o 2016 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1049/iet-pel.2017.0528` | Modified hybrid model of boost converters for parameter identification of passive compon | IET Power Electronics 2018 | `03_CM_ParameterEstimation` |

### MDPI（3 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L2 | 3 | `10.1109/peds.2007.4487736` | Using DFT to Obtain the Equivalent Circuit of Aluminum Electrolytic Capacitors | 2007 7th International Conference  2007 | `03_CM_ParameterEstimation` |
| L2 | 2 | `10.1109/peds.2005.1619949` | An ESR Meter for High Frequencies | 2005 International Conference on P  | `00_Reviews_Capacitor` |
| L2 | 2 | `10.1109/cpe.2016.7544180` | Condition monitoring of dc-link capacitor utilizing zero state of solar PV H5 inverter | 2016 10th International Conference 2016 | `03_CM_ParameterEstimation` |

## D 组 — 支撑文献　（15 篇）

引用级，非必读。

### IEEE Xplore（10 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L4 | 1 | `10.1109/apec42165.2021.9487107` | Condition Monitoring of DC-Link Capacitors Using Hidden Markov Model Supported-Convoluti | 2021 IEEE Applied Power Electronic 2021 | `05_DataDriven_AI` |
| L3 | 1 | `10.1109/tpel.2017.2691048` | Online Evaluation Method of Electrolytic Capacitor Degradation for Digitally Controlled  | IEEE Transactions on Power Electro 2018 | `03_CM_ParameterEstimation` |
| L3 | 1 | `10.1109/aero.2007.352885` | A Prognostic Sensor for Voltage Regulated Switch-Mode Power Supplies | 2007 IEEE Aerospace Conference 2007 | `03_CM_ParameterEstimation` |
| L2 | 1 | `10.1109/tpel.2020.3009600` | A Digital Twin Based Estimation Method for Health Indicators of DC–DC Converters | IEEE Transactions on Power Electro 2021 | `06_PhysicsInformed_DigitalTwin` |
| L2 | 1 | `10.1109/tpel.2009.2017806` | Condition Monitoring of Power Electronic Circuits Using Artificial Neural Networks | IEEE Transactions on Power Electro 2009 | `05_DataDriven_AI` |
| L2 | 1 | `10.1109/ecce.2019.8912199` | Application of Digital Twin Concept in Condition Monitoring for DC-DC Converter | 2019 IEEE Energy Conversion Congre 2019 | `06_PhysicsInformed_DigitalTwin` |
| L2 | 1 | `10.1109/tim.2020.3001368` | Prediction of Capacitor’s Accelerated Aging Based on Advanced Measurements and Deep Neur | IEEE Transactions on Instrumentati 2020 | `05_DataDriven_AI` |
| L2 | 1 | `10.1109/tpel.2024.3409534` | Capacitor Parameter Estimation Based on Wavelet Transform and Convolution Neural Network | IEEE Transactions on Power Electro 2024 | `05_DataDriven_AI` |
| L2 | 1 | `10.1109/ecce.2009.5316418` | Kalman filter used for on line monitoring and predictive maintenance system of aluminium | 2009 IEEE Energy Conversion Congre 2009 | `03_CM_ParameterEstimation` |
| L1 | 1 | `10.1109/ecce50734.2022.9947826` | Converter Circuits to Machine Learning: Optimal Feature Selection | 2022 IEEE Energy Conversion Congre 2022 | `05_DataDriven_AI` |

### Other（3 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L2 | 1 | `10.1109/phm2022-london52454.2022.00053` | Circuit Parameter Identification of Degrading DC-DC Converters Based on Physics-informed | 2022 Prognostics and Health Manage 2022 | `06_PhysicsInformed_DigitalTwin` |
| L2 | 1 | `10.1109/picc57976.2023.10142579` | Condition Monitoring of Submodule Capacitors in Modular Multilevel Converter Using Digit | 2023 International Conference on P 2023 | `06_PhysicsInformed_DigitalTwin` |
| n/a | 1 | `10.1016/j.egyr.2021.10.116` | Digital twin accelerating development of metallized film capacitor: Key issues, framewor | Energy Reports 2021 | `06_PhysicsInformed_DigitalTwin` |

### MDPI（1 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L3 | 1 | `10.1109/pedstc.2016.7556887` | A noninvasive on-line failure prediction technique for aluminum electrolytic capacitors  | 2016 7th Power Electronics and Dri 2016 | `03_CM_ParameterEstimation` |

### Elsevier（1 篇）

| 等级 | 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---|---:|---|---|---|---|
| L2 | 1 | `10.1016/j.microrel.2017.11.002` | Prognostics of aluminum electrolytic capacitors using artificial neural network approach | Microelectronics Reliability 2018 | `05_DataDriven_AI` |

---

## 说明

- **等级列**是 PHM 能力分级（L0–L7），标注方法实际*输出*什么，不是标题声称什么。L2=参数估计，L3=检测/诊断，L5=SOH 状态估计，L6=RUL 预测，L7=维护决策。加粗的是 L5+。
- 所有 DOI 来自综述自身的参考文献列表，并逐条经 Crossref 解析核验，**无任何推测项**。
- 直接访问 `https://doi.org/<DOI>` 跳转出版商页面。
- 文件名不必照抄，我按内容识别；**放对 `归档目录` 列即可**。
- 会议论文若机构无权限可跳过，Stage 2 会用期刊扩展版替代。

## 建议顺序

**只下 A 组也能推进** —— 那 16 篇是第 5、6 章的全部证据基础，也是最可能改变结论的部分。B/C 组用于方法比较表，可以后续分批补。
