# 需要您下载的论文（Stage 1 共被引正典）

**机读版本：** [papers_to_obtain_stage1.csv](papers_to_obtain_stage1.csv)

## 这份清单是怎么来的

OpenAlex 被 IP 级限流、Crossref 相关度检索召回率只有 50%，两条路都走不通。
改用**共被引分析**：把 10 篇综述（9 篇电容综述 + Yang 2010 器件综述）在 Crossref 上
登记的参考文献全部取出，得到 **619 篇唯一文献**，然后按「被多少篇*独立*综述同时引用」排序。
被多篇独立综述共同引用的论文，就是这个领域的专家共识正典——这个信号不依赖任何相关度排序函数。

| 共引次数 | 篇数 |
|---|---:|
| 6 篇综述 | 5 |
| 5 篇 | 7 |
| 4 篇 | 33 |
| 3 篇 | 25 |
| 2 篇 | 57 |
| 1 篇 | 492 |

我已经通过 Unpaywall 确认 OA 后自动下载了 **65 篇**，库存从 12 篇增至 **82 篇**。
下面是**剩下需要您用机构权限获取的**——只列被 ≥2 篇综述共引的核心文献。

---

## Tier A — 被 4 篇以上综述共引（领域正典，最高优先）　（39 篇）

### IEEE Xplore（36 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 6 | `10.1109/63.261004` | Use of ESR for deterioration diagnosis of electrolytic capacitor | IEEE Transactions on Power Electronics 1993 | `03_CM_ParameterEstimation` |
| 6 | `10.1109/tia.2010.2049972` | A Real-Time Predictive-Maintenance System of Aluminum Electrolytic Capacitors Used in Uninterru | IEEE Transactions on Industry Applicat 2010 | `04_SOH_RUL_Prognostics` |
| 6 | `10.1109/2943.974353` | Realization of a Smart: Electrolytic Capacitor Circuit: Electrolytic Capacitor Circuits that ca | IEEE Industry Applications Magazine 2002 | `03_CM_ParameterEstimation` |
| 6 | `10.1109/tia.2012.2222333` | Condition Monitoring of DC-Link Capacitors in Aerospace Drives | IEEE Transactions on Industry Applicat 2012 | `03_CM_ParameterEstimation` |
| 5 | `10.1109/tpel.2010.2059713` | Life-Cycle Monitoring and Voltage-Managing Unit for DC-Link Electrolytic Capacitors in PWM Conv | IEEE Transactions on Power Electronics 2011 | `02_Failure_Physics` |
| 5 | `10.1109/tie.2012.2218561` | Fault Diagnosis of DC-Link Capacitors in Three-Phase AC/DC PWM Converters by Online Estimation  | IEEE Transactions on Industrial Electr 2013 | `03_CM_ParameterEstimation` |
| 5 | `10.1109/tie.2009.2022077` | A Simple Offline Technique for Evaluating the Condition of Aluminum–Electrolytic–Capacitors | IEEE Transactions on Industrial Electr 2009 | `03_CM_ParameterEstimation` |
| 5 | `10.1109/tpel.2017.2736162` | Quasi-Online Technique for Health Monitoring of Capacitor in Single-Phase Solar Inverter | IEEE Transactions on Power Electronics 2018 | `03_CM_ParameterEstimation` |
| 5 | `10.1109/pesc.2005.1582040` | A Real Time Method to Estimate Electrolytic Capacitor Condition in PWM Adjustable Speed Drives  | IEEE 36th Conference on Power Electron  | `03_CM_ParameterEstimation` |
| 5 | `10.1109/tim.2008.925013` | An Economic Offline Technique for Estimating the Equivalent Circuit of Aluminum Electrolytic Ca | IEEE Transactions on Instrumentation a 2008 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tia.2011.2124436` | An Industry-Based Survey of Reliability in Power Electronic Converters | IEEE Transactions on Industry Applicat 2011 | `00_Reviews_Capacitor` |
| 4 | `10.1109/63.728347` | Failure prediction of electrolytic capacitors during operation of a switchmode power supply | IEEE Transactions on Power Electronics 1998 | `04_SOH_RUL_Prognostics` |
| 4 | `10.1109/tvt.2012.2206082` | Analysis and Evaluation of DC-Link Capacitors for High-Power-Density Electric Vehicle Drive Sys | IEEE Transactions on Vehicular Technol 2012 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tia.2005.858258` | Life Prediction Modeling of Bus Capacitors in AC Variable-Frequency Drives | IEEE Transactions on Industry Applicat 2005 | `04_SOH_RUL_Prognostics` |
| 4 | `10.1109/tie.2007.903975` | Online Failure Prediction of the Electrolytic Capacitor for LC Filter of Switching-Mode Power C | IEEE Transactions on Industrial Electr 2008 | `04_SOH_RUL_Prognostics` |
| 4 | `10.1109/tpel.2014.2339374` | Deterioration Monitoring of DC-Link Capacitors in AC Machine Drives by Current Injection | IEEE Transactions on Power Electronics 2015 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tim.2009.2032960` | An Online and Noninvasive Technique for the Condition Monitoring of Capacitors in Boost Convert | IEEE Transactions on Instrumentation a 2010 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tpel.2014.2383436` | A Current-Sensorless Online ESR and C Identification Method for Output Capacitor of Buck Conver | IEEE Transactions on Power Electronics 2015 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tia.2008.2002181` | DC-Link Capacitance Estimation in AC/DC/AC PWM Converters Using Voltage Injection | IEEE Transactions on Industry Applicat 2008 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tie.2018.2835393` | A VEN Condition Monitoring Method of DC-Link Capacitors for Power Converters | IEEE Transactions on Industrial Electr 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tpel.2019.2951859` | Condition Monitoring of DC-Link Capacitors Using Goertzel Algorithm for Failure Precursor Param | IEEE Transactions on Power Electronics 2020 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tpel.2018.2890617` | An Online ESR Estimation Method for Output Capacitor of Boost Converter | IEEE Transactions on Power Electronics 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tia.2002.802922` | The service life of large aluminum electrolytic capacitors: effects of construction and applica | IEEE Transactions on Industry Applicat 2002 | `02_Failure_Physics` |
| 4 | `10.1109/tpel.2018.2857832` | Reference Submodule Based Capacitor Monitoring Strategy for Modular Multilevel Converters | IEEE Transactions on Power Electronics 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/apex.2007.357646` | Real-Time Condition Monitoring of the Electrolytic Capacitors for Power Electronics Application | APEC 07 - Twenty-Second Annual IEEE Ap 2007 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/ecce.2014.6953683` | Condition monitoring of submodule capacitors in modular multilevel converters | 2014 IEEE Energy Conversion Congress a 2014 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tpel.2017.2762341` | Noninvasive Technique for DC-Link Capacitance Estimation in Single-Phase Inverters | IEEE Transactions on Power Electronics 2018 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tpel.2019.2917937` | Condition Monitoring for Submodule Capacitors in Modular Multilevel Converters | IEEE Transactions on Power Electronics 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tim.2009.2019719` | Condition Monitoring of Metallized Polypropylene Film Capacitors in Railway Power Trains | IEEE Transactions on Instrumentation a 2009 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tie.2018.2880725` | Health Estimation of Individual Capacitors in a Bank With Reduced Sensor Requirements | IEEE Transactions on Industrial Electr 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/tim.2017.2749838` | Noninvasive Online Condition Monitoring of Output Capacitor’s ESR and C for a Flyback Converter | IEEE Transactions on Instrumentation a 2017 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/isie.2007.4374704` | Using Newton-Raphson Method to Estimate the Condition of Aluminum Electrolytic Capacitors | 2007 IEEE International Symposium on I 2007 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/jsen.2019.2945943` | Online Monitoring of Aluminum Electrolytic Capacitors in Photovoltaic Systems by Magnetoresisti | IEEE Sensors Journal 2020 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/jsen.2019.2929537` | Condition Monitoring of Electrolytic Capacitors in Boost Converters by Magnetic Sensors | IEEE Sensors Journal 2019 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/iecon.2008.4758011` | An automatic technique to obtain the equivalent circuit of aluminum electrolytic capacitors | 2008 34th Annual Conference of IEEE In 2008 | `03_CM_ParameterEstimation` |
| 4 | `10.1109/demped.2009.5292791` | Using input current and output voltage ripple to estimate the output filter condition of switch | 2009 IEEE International Symposium on D 2009 | `03_CM_ParameterEstimation` |

### IET（3 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 4 | `10.1049/ip-epa:20050027` | Online capacitance estimation of DC-link electrolytic capacitors for three-phase AC/DC/AC PWM c | IEE Proceedings - Electric Power Appli 2005 | `03_CM_ParameterEstimation` |
| 4 | `10.1049/iet-pel.2016.0603` | Capacitor impedance estimation utilizing dc‐link voltage oscillations in single phase inverter | IET Power Electronics 2017 | `03_CM_ParameterEstimation` |
| 4 | `10.1049/iet-pel.2018.5394` | Online estimation scheme of output capacitor's ESR and tan
                    δ
               | IET Power Electronics 2019 | `03_CM_ParameterEstimation` |

## Tier B — 被 3 篇综述共引　（18 篇）

### IEEE Xplore（16 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 3 | `10.1109/tpel.2015.2496267` | An Online Monitoring Scheme of DC-Link Capacitor's ESR and C for a Boost PFC Converter | IEEE Transactions on Power Electronics 2016 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/tdmr.2006.876612` | Linking Corrosion and Catastrophic Failure in Low-Power Metallized Polypropylene Capacitors | IEEE Transactions on Device and Materi 2006 | `02_Failure_Physics` |
| 3 | `10.1109/tie.2017.2674598` | Low-Frequency Impedance Monitoring and Corresponding Failure Criteria for Aluminum Electrolytic | IEEE Transactions on Industrial Electr 2017 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/tie.2016.2582470` | Online Monitoring Technique for Aluminum Electrolytic Capacitor in Solar PV-Based DC System | IEEE Transactions on Industrial Electr 2016 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/tpel.2019.2904551` | High-Accuracy Capacitance Monitoring of DC-Link Capacitor in VSI Systems by
                    | IEEE Transactions on Power Electronics 2019 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/powereng.2015.7266382` | Condition monitoring for DC-link capacitors based on artificial neural network algorithm | 2015 IEEE 5th International Conference 2015 | `05_DataDriven_AI` |
| 3 | `10.1109/tim.2009.2038018` | Simple Experimental Techniques to Characterize Capacitors in a Wide Range of Frequencies and Te | IEEE Transactions on Instrumentation a 2010 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/tpel.2018.2868564` | A Noninvasive Online Monitoring Method of Output Capacitor's C and ESR for DCM Flyback Converte | IEEE Transactions on Power Electronics 2019 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/ifeec.2017.7992442` | Artificial Neural Network based DC-link capacitance estimation in a diode-bridge front-end inve | 2017 IEEE 3rd International Future Ene 2017 | `05_DataDriven_AI` |
| 3 | `10.1109/imtc.2006.328273` | An Experimental Technique for Estimating the ESR and Reactance Intrinsic Values of Aluminum Ele | 2006 IEEE Instrumentation and Measurem 2006 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/ccece.2015.7129353` | Capacitor aging detection for the DC filters in the power electronic converters using ANFIS alg | 2015 IEEE 28th Canadian Conference on  2015 | `02_Failure_Physics` |
| 3 | `10.1109/isie.2004.1572002` | Use of ESR to predict failure of output filtering capacitors in boost converters | 2004 IEEE International Symposium on I 2004 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/isie.2010.5637333` | Estimating aluminum electrolytic capacitors condition using a low frequency transformer togethe | 2010 IEEE International Symposium on I 2010 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/vppc.2012.6422642` | Condition monitoring of DC-link capacitors in drive system for electric vehicles | 2012 IEEE Vehicle Power and Propulsion 2012 | `03_CM_ParameterEstimation` |
| 3 | `10.1109/icit.2005.1600615` | An Experimental Technique for Estimating the Aluminum Electrolytic Capacitor Equivalent Circuit | 2005 IEEE International Conference on   | `03_CM_ParameterEstimation` |
| 3 | `10.1109/pesc.2008.4592252` | A non-invasive technique for fault diagnosis of SMPS | 2008 IEEE Power Electronics Specialist 2008 | `03_CM_ParameterEstimation` |

### IET（1 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 3 | `10.1049/iet-pel.2011.0163` | On-line fault detection of aluminium electrolytic capacitors, in step-down DC–DC converters, us | IET Power Electronics 2012 | `03_CM_ParameterEstimation` |

### MDPI（1 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 3 | `10.1109/peds.2007.4487736` | Using DFT to Obtain the Equivalent Circuit of Aluminum Electrolytic Capacitors | 2007 7th International Conference on P 2007 | `03_CM_ParameterEstimation` |

## Tier C — 被 2 篇综述共引　（47 篇）

### IEEE Xplore（34 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 2 | `10.1109/mei.2010.5383924` | Historical introduction to capacitor technology | IEEE Electrical Insulation Magazine 2010 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/iecon.2012.6388833` | Design for reliability of power electronic systems | IECON 2012 - 38th Annual Conference on 2012 | `02_Failure_Physics` |
| 2 | `10.1109/tia.2008.2002220` | Condition Monitoring of DC-Link Electrolytic Capacitors in Adjustable-Speed Drives | IEEE Transactions on Industry Applicat 2008 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpel.2016.2552039` | Application of an Efficient Rogowski Coil Sensor for Switch Fault Diagnosis and Capacitor ESR M | IEEE Transactions on Power Electronics 2017 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tie.2016.2581156` | PoF-Simulation-Assisted Reliability Prediction for Electrolytic Capacitor in LED Drivers | IEEE Transactions on Industrial Electr 2016 | `02_Failure_Physics` |
| 2 | `10.1109/tpel.2015.2472459` | Low Sampling Rate Online Parameters Monitoring of DC–DC Converters for Predictive-Maintenance U | IEEE Transactions on Power Electronics 2016 | `04_SOH_RUL_Prognostics` |
| 2 | `10.1109/tie.2017.2652372` | Online Condition Monitoring for Both IGBT Module and DC-Link Capacitor of Power Converter Based | IEEE Transactions on Industrial Electr 2017 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tie.2019.2912771` | Failure Prediction of Submodule Capacitors in Modular Multilevel Converter by Monitoring the In | IEEE Transactions on Industrial Electr 2020 | `04_SOH_RUL_Prognostics` |
| 2 | `10.1109/tste.2014.2347967` | Performance Evaluation of Three-Phase Grid-Connected Photovoltaic Inverters Using Electrolytic  | IEEE Transactions on Sustainable Energ 2014 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tia.2018.2836923` | Online Estimation of Aluminum Electrolytic-Capacitor Parameters Using a Modified Prony's Method | IEEE Transactions on Industry Applicat 2018 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpel.2019.2957027` | Online Estimation of ESR for DC-Link Capacitor of Boost PFC Converter Using Wavelet Transform B | IEEE Transactions on Power Electronics 2020 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/ecce.2017.8096961` | Capacitance estimation algorithm based on DC-link voltage harmonics using artificial neural net | 2017 IEEE Energy Conversion Congress a 2017 | `05_DataDriven_AI` |
| 2 | `10.1109/tie.2021.3055164` | ESR Estimation for Aluminum Electrolytic Capacitor of Power Electronic Converter Based on Compr | IEEE Transactions on Industrial Electr 2022 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpel.2010.2062200` | A New Strategy for Condition Monitoring of Adjustable Speed Induction Machine Drive Systems | IEEE Transactions on Power Electronics 2011 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpel.2019.2959074` | Online Capacitance Estimation of Submodule Capacitors for Modular Multilevel Converter With Nea | IEEE Transactions on Power Electronics 2020 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tie.2016.2586020` | Lifetime Monitoring of Electrolytic Capacitor to Maximize Earnings From Grid-Feeding PV System | IEEE Transactions on Industrial Electr 2016 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/pesc.2005.1581687` | Condition Monitoring of Electrolytic Capacitor in Power Electronic Circuits using Adaptive Filt | IEEE 36th Conference on Power Electron  | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpel.2021.3135873` | Condition Monitoring of DC-Link Capacitors Using Time–Frequency Analysis and Machine Learning C | IEEE Transactions on Power Electronics 2022 | `05_DataDriven_AI` |
| 2 | `10.1109/tpel.2021.3121813` | Aging Condition Monitoring for Aluminum Electrolytic Capacitor in Variable Speed Drives | IEEE Transactions on Power Electronics 2022 | `02_Failure_Physics` |
| 2 | `10.1109/ipemc.2016.7512885` | Capacitance estimation for dc-link capacitors in a back-to-back converter based on Artificial N | 2016 IEEE 8th International Power Elec 2016 | `05_DataDriven_AI` |
| 2 | `10.1109/tpmp.1965.1135396` | The Chemistry of Failure of Aluminum Electrolytic Capacitors | IEEE Transactions on Parts, Materials  1965 | `02_Failure_Physics` |
| 2 | `10.1109/tpel.2021.3118602` | Condition Health Monitoring of Modular Multilevel Converter Submodule Capacitors | IEEE Transactions on Power Electronics 2022 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/apec.2005.1453106` | Failure prediction of electrolytic capacitor using DSP methods | Twentieth Annual IEEE Applied Power El  | `04_SOH_RUL_Prognostics` |
| 2 | `10.1109/iecon.2009.5414963` | State condition estimation of aluminum electrolytic capacitors used on the primary side of ATX  | 2009 35th Annual Conference of IEEE In 2009 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/pesc.2005.1582038` | Parameter Identification of Power Electronic Circuits Based on Hybrid Model | IEEE 36th Conference on Power Electron  | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tcsii.2020.3040428` | Switching Signals Based Condition Monitoring for Submodule Capacitors in Modular Multilevel Con | IEEE Transactions on Circuits and Syst 2021 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/ipemc-ecceasia48364.2020.9367704` | Online Monitoring for Sub-module Capacitance in Modular Multilevel Converter with Four Sampling | 2020 IEEE 9th International Power Elec 2020 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/tpwrd.2022.3176001` | A Hierarchic Capacitor Condition Monitoring Strategy for High-Voltage Modular Multilevel Conver | IEEE Transactions on Power Delivery 2022 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/icit.2015.7125215` | An online technique for condition monitoring of capacitor in PV system | 2015 IEEE International Conference on  2015 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/iecon.2017.8216161` | Capacitor monitoring for modular multilevel converters | IECON 2017 - 43rd Annual Conference of 2017 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/iecon.2005.1569015` | LMS based condition monitoring of electrolytic capacitor | 31st Annual Conference of IEEE Industr 2005 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/ecce.2014.6953873` | A novel online ESR and C identification method for output capacitor of buck converter | 2014 IEEE Energy Conversion Congress a 2014 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/iecon.2019.8927539` | Capacitor Monitoring for Full-Bridge Submodule Based Modular Multilevel Converters | IECON 2019 - 45th Annual Conference of 2019 | `03_CM_ParameterEstimation` |
| 2 | `10.1109/ias.2007.346` | ESR Estimation Method for DC/DC Converters Through Simplified Regression Models | 2007 IEEE Industry Applications Annual 2007 | `03_CM_ParameterEstimation` |

### Other（5 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 2 | `10.1007/s00202-004-0265-z` | Simple model of an electrolytic capacitor taking into account the temperature and aging time | Electrical Engineering 2006 | `02_Failure_Physics` |
| 2 | `10.1109/ectc.1998.678924` | A new technique for high frequency characterization of capacitors | 1998 Proceedings. 48th Electronic Comp  | `03_CM_ParameterEstimation` |
| 2 | `10.1109/powereng.2009.4915158` | Using a sinosoidal PWM to estimate the ESR of Aluminum electrolytic capacitors | 2009 International Conference on Power 2009 | `03_CM_ParameterEstimation` |
| 2 | `10.1177/1687814018781170` | An intelligent prognostic model for electrolytic capacitors health monitoring: A design of expe | Advances in Mechanical Engineering 2018 | `04_SOH_RUL_Prognostics` |
| 2 | `10.1109/phm-chongqing.2018.00143` | Online Output Capacitor Monitor for Buck DC-DC Converter | 2018 Prognostics and System Health Man 2018 | `04_SOH_RUL_Prognostics` |

### Elsevier（4 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 2 | `10.1016/j.microrel.2016.07.110` | Detection of cracks in multilayer ceramic capacitors by X-ray imaging | Microelectronics Reliability 2016 | `02_Failure_Physics` |
| 2 | `10.1109/imccc.2012.199` | Fault Diagnosis and Life Prediction of DC-link Aluminum Electrolytic Capacitors Used in Three-p | 2012 Second International Conference o 2012 | `04_SOH_RUL_Prognostics` |
| 2 | `10.1002/(sici)1099-1638(199601)12:1<43::aid-qre981>3.0.co;2-o` | NON-DESTRUCTIVE DETECTION AND LOCALIZATION OF DEFECTS IN MULTILAYER CERAMIC CHIP CAPACITORS USI | Quality and Reliability Engineering In 1996 | `02_Failure_Physics` |
| 2 | `10.1016/j.microrel.2020.113737` | A method to extract lumped thermal networks of capacitors for reliability oriented design | Microelectronics Reliability 2020 | `02_Failure_Physics` |

### IET（2 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 2 | `10.1049/cp.2016.0369` | A New Scheme for Monitoring Submodule Capacitance in Modular Multilevel Converter | 8th IET International Conference on Po 2016 | `03_CM_ParameterEstimation` |
| 2 | `10.1049/iet-pel.2017.0528` | Modified hybrid model of boost converters for parameter identification of passive components | IET Power Electronics 2018 | `03_CM_ParameterEstimation` |

### MDPI（2 篇）

| 共引 | DOI | 标题 | 期刊 / 年 | 归档目录 |
|---:|---|---|---|---|
| 2 | `10.1109/peds.2005.1619949` | An ESR Meter for High Frequencies | 2005 International Conference on Power  | `03_CM_ParameterEstimation` |
| 2 | `10.1109/cpe.2016.7544180` | Condition monitoring of dc-link capacitor utilizing zero state of solar PV H5 inverter | 2016 10th International Conference on  2016 | `03_CM_ParameterEstimation` |

---

## 下载说明

- 所有 DOI 均来自综述参考文献列表并经 Crossref 逐条解析核验，无推测项。
- 直接访问 `https://doi.org/<DOI>` 即可跳转到出版商页面。
- 文件名不必严格照抄，我会按内容识别；**放对目录即可**（`归档目录` 列）。
- 会议论文（`proceedings-article`）如机构无权限可跳过，我会在 Stage 2 用期刊扩展版替代。
