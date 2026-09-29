# Teardown-Based cell-to-pack scaling of capacity and resistance in field-aged EV battery packs

Marco Fischer<sup>a,∗</sup>, Martin J. Brand<sup>a,b</sup>, Alexander Schröder<sup>c</sup>, Andreas Jossen<sup>a</sup>

<sup>a</sup> *Technical University of Munich (TUM), TUM School of Engineering and Design; Department of Energy and Process Engineering, Chair of Electrical Energy Storage Technology (EES), Arcisstr. 21, 80333 Munich, Germany*<br><sup>b</sup> *Li.plus GmbH, Bergmannstr. 49, 80339 Munich, Germany*<br><sup>c</sup> *TES-AMM Central Europe GmbH, Blitzkuhlenstraße 169, 45659 Recklinghausen, Germany*

## Article info

*Keywords:* EV battery pack; Teardown; Lithium-ion battery; State of health; Ohmic resistance; DC-pulse resistance; Component-resolved characterization; Scaling

∗ Corresponding author.

*E-mail address:* marco.fischer@tum.de (M. Fischer).

https://doi.org/10.1016/j.etran.2026.100636

Received 6 July 2026; Received in revised form 27 August 2026; Accepted 14 September 2026

Available online 18 September 2026

2590-1168/© 2026 The Authors. Published by Elsevier B.V. This is an open access article under the CC BY license ( http://creativecommons.org/licenses/by/4.0/ ). Open access funding enabled and organized by Projekt DEAL.

## Abstract

Evidence on how capacity and resistance scale from individual cells to entire packs in electric vehicles remains limited, particularly when accounting for non-cell contributions and measurement uncertainties. This study presents an in-depth case study of 3 field-aged electric vehicle battery packs. A matched teardown workflow links logical-cell capacity with resistance measurements of intact packs, modules, logical cells, module connectors, and the high-voltage disconnect (HVD). The early-time ohmic resistance *R*<sub>Ω</sub> is determined consistently across all hierarchy levels, while uncertainty propagation is used to assess component-to-pack closure. For the packs characterized 5 to 6 years after manufacturing, the minimum logical-cell capacities correspond to capacity-based state-of-health estimates of 92.8 % to 95.2 %. A literature-based translation to energy retention places all 3 estimates above the current Euro 7 threshold. Logical-cell capacity coefficients of variation range from 0.15 % to 0.41 %, while *R*<sub>Ω</sub> resolves resistance heterogeneity across all 3 packs. Non-cell contributions from module connectors and the HVD account for 2.9 % to 4.3 % of total pack ohmic resistance. Cell-to-pack *R*<sub>Ω</sub> residuals remain below 1.5 %, and module-to-pack residuals remain below 0.9 %. In contrast, cell-to-pack DC-pulse resistance residuals range from −2.8 % to 8.3 %. Under the applied protocol and instrumentation, early-time *R*<sub>Ω</sub> provides tighter component closure and resolves dispersion with lower uncertainty, supporting the development of component-level quality gates. Capacity and DC-pulse resistance offer complementary insights into limiting logical cells and aging.

## 1. Introduction

The scalability of lithium-ion batteries (LIBs), combined with their high power and energy density, makes them the leading technology among rechargeable energy storage systems. By connecting cells in series and parallel, power capability and capacity can be tailored to the requirements of specific applications. As a result, LIBs have become the preferred energy source for mobile applications and electric vehicles (EVs) [1,2].

At the same time, battery packs are heterogeneous multi-component systems in which cell-to-cell variations and parasitic resistances can bias pack-level diagnostics and complicate reliable state estimation [3–7]. Despite their relevance to lifetime assessment and diagnostics, only a limited number of studies report component-resolved datasets for field-aged cells, modules, and packs, including interconnection topology and electrical and electrochemical characteristics [8–10]. As packs age, differences in capacity and resistance between cells can either increase or decrease, depending on balancing strategy, thermal gradients, and contact resistances [11–19]. Yet, only a few studies quantify such inhomogeneities in aged packs with measurements that consistently link pack, module, and cell levels.

At the pack and system levels, standards and regulations define harmonized test procedures and reporting conventions for quantifying performance metrics such as capacity, energy, and power capability. These frameworks enable reproducible benchmarking across suppliers and original equipment manufacturers (OEMs) [20–23]. For example, ISO 12405-4:2018 [20] specifies performance testing of traction battery packs and systems, including capacity and energy tests, as well as resistance characterization using DC pulses across different C-rates, temperatures, and SOCs. While these procedures are essential for validation and acceptance testing, they primarily focus on pack-level assessment at begin of life (BOL) and do not address how cells and interconnects contribute to the measured pack-level result. Recent work by Rüther et al. [3] further underscores the need for clear pack-level definitions and descriptors to improve comparability and reduce misinterpretation in heterogeneous systems. In this context, the authors propose the state of homogeneity (SOHo) as an additional descriptor for packs and subcomponents.

In contrast, cell testing provides a broad set of methods for electrical and electrochemical diagnostics, although standardized protocols for several workflows are still evolving [24,25]. Widely used approaches include DC-pulse and electrochemical impedance spectroscopy (EIS) measurements [26–28], often interpreted using distribution of relaxation times (DRT) or an equivalent circuit model (ECM) [29]. Both resistance and impedance are sensitive to SOC, temperature, and aging [27,28], supporting state estimation and degradation modeling [26,28,30]. However, transferring insights from single cells to battery packs remains challenging, as local states can differ across cells and modules, potentially blurring or masking features observed at the pack level. Recent vehicle-level studies demonstrate that differential-voltage and incremental-capacity features can be transferred from cells to EV charging measurements [31]. A subsequent study showed that the resulting diagnostic features can be reproduced when relevant boundary conditions, including charging power and temperature, are controlled [32]. However, the limited availability of representative field data and validation under practical operating conditions remains a barrier to the industrial transfer of battery-health diagnostics [33]. These approaches complement but do not replace component-resolved measurements that localize cell and non-cell contributions within the pack. Thus, measurements at the pack, module, and cell levels are needed to identify and quantify such deviations within battery systems.

[Fig. 1](../assets/figure/figure-1.jpg)

**Fig. 1.** Conceptual overview of the study design and main case-study outcomes. (a) Motivation, scope, and research questions. (b) Matched teardown and measurement workflow for the three field-aged packs, including the pack architectures, test conditions, investigated quantities, component levels, and sample sizes. (c) Analyses of dispersion, measurement uncertainty, and resistance additivity and closure. (d) Main aging results based on the limiting logical cell of each pack, capacity and ohmic-resistance dispersion, and component-to-pack closure.

Teardown studies provide valuable insight into battery systems by linking selected cell-, module-, and vehicle-level properties [1,10]. However, field-aged investigations have mainly characterized extracted modules or cells after disassembly and do not quantify how the lower-level contributions reconstruct the intact-pack response [17,34]. Recent second-life studies have extended such assessments by using EIS-derived features or partial DC-pulse curves for capacity estimation and have supported the regrouping of retired EV cells [35,36]. Still, these approaches do not combine logical-cell capacity measurements with a matched resistance dataset spanning the intact pack, modules, logical cells, module connectors, and the HVD. Comparison across studies is further complicated since resistance strongly depends on SOC, temperature, C-rate, pulse duration, and state of health (SOH) [8,26,27,30,37,38]. As a result, pack and module inhomogeneities in field-aged packs remain insufficiently documented, especially when connector resistances are measured explicitly and compared on a like-for-like basis.

These gaps motivate an in-depth case study of 3 field-aged EV battery packs, linking logical-cell observations to measurable properties of modules, intact packs, and non-cell hardware. In this study, we introduce a component-resolved workflow that combines a systematic teardown with uncertainty-aware resistance closure to assess dispersion and resistance scaling. The early-time ohmic resistance *R*<sub>Ω</sub> is consistently determined at each hierarchy level using a method described in a previous patent [39]. The resulting attribution separates cell and non-cell contributions and provides a basis for component-level diagnostics and quality assessment. Results from a sample of three battery packs from a single vehicle model and one cell type provide a limited perspective, making it impossible to draw broader conclusions.

Our capacity analysis assesses the distribution of logical-cell capacities across modules and packs, where a logical cell denotes a group of parallel-connected cells that constitutes a single series element of the pack [3]. Since capacity was measured only after teardown at the logical-cell level, the minimum logical-cell capacity is used as a proxy for the remaining pack capacity. For context, this proxy is compared with the Euro 7 energy-retention thresholds of 80 % and 72 % after 5 years or 100 000 km and after 8 years or 160 000 km, respectively [40]. Since Euro 7 defines battery durability at the vehicle level in terms of usable energy, this comparison is approximate and does not constitute a formal compliance assessment. The resistance analysis complements this capacity assessment by quantifying instrument and repeatability uncertainty, resolving the contributions of logical cells, module connectors, and the HVD to total pack resistance, and quantifying pack variability for ohmic and DC-pulse resistance at 1 s, 10 s and 30 s. Finally, we evaluate how accurately a simple resistance network predicts module and pack resistances, and identify the scaling errors arising from cell-to-module, module-to-pack, and cell-to-pack scaling.

Fig. 1 summarizes the research questions, the matched teardown and measurement workflow, the analyses of dispersion and measurement uncertainty, the resistance-additivity assessment, and the main case-study results.

## 2. Experimental setup and methodology

### 2.1. Test objects, measurement procedures, and numbering

We investigated 3 field-aged EV battery packs and their subcomponents, focusing on their electrical and electrochemical characteristics, as detailed in Section 2.3. Table 1 summarizes the cell and pack specifications together with the electrical parameters determined in this study. All packs were removed from Hyundai Kona Electric vehicles and contained LGY E63B cells from LG Chem with a nominal capacity *C*<sub>N</sub> of 63 Ah, a nominal voltage *U*<sub>N</sub> of 3.63 V, and a voltage window of 2.5 V to 4.2 V. According to the manufacturer’s datasheet, the dimensions of the pouch cells are 14.5 mm × 100 mm × 301 mm (H × W × L) and the weight is 882 g. In the following, the term logical cell refers to a group of cells that are connected in parallel [3]. These parallel groups are then connected in series to achieve the specific system voltage required for the application. Measurements at this level treat each parallel group as a single electrical entity and cannot resolve differences among the cells connected in parallel.

Pack 1 was manufactured on June 30, 2020, and consisted of 90 logical cells connected in series. Each logical cell was composed of 2 cells connected in parallel, resulting in a nominal pack capacity of 126 Ah and a nominal voltage of 324 V. These logical cells were distributed across 6 modules, with each module containing 15 logical cells. The modules were interconnected by 9 connectors, including the HVD. Packs 2 and 3 were manufactured on March 26, 2019, and May 14, 2019, respectively. Both packs contained 98 logical cells connected in series, with each logical cell containing 3 cells connected in parallel, resulting in a nominal pack capacity of 189 Ah and a nominal voltage of 352.8 V. They were divided into 10 modules and interconnected by 13 connectors, including the HVD. Most modules of Packs 2 and 3 comprised 10 logical cells connected in series, whereas Modules 4 and 6 each comprised 9 logical cells. The corresponding pack architectures are illustrated in Fig. 2 (a) for Pack 1 and Fig. 2 (b) for Packs 2 and 3, respectively. In both configurations, numbering starts at the global negative pack terminal and increases towards the global positive pack terminal. The figure further highlights the module connectors C<sub>x,y</sub> between adjacent modules, thereby providing the structural basis for the subsequent analysis of capacity and resistance at the pack, module, logical-cell, and connector levels. Beyond the manufacturing dates and vehicle model listed in Table 1, detailed field-operation histories were unavailable.

**Table 1**

Battery cell and pack specifications, investigated electrical parameters, and investigated components of the field-aged Hyundai Kona Electric vehicle battery packs.

[Table 1](../assets/table/table-1.csv)

| Cell specifications |  |  |  |
| --- | --- | --- | --- |
| Manufacturer | LG Chem, Ltd. |  |  |
| Cell identifier | LGY E63B |  |  |
| C_N | 63 Ah |  |  |
| U_N | 3.63 V |  |  |
| Voltage range | 2.5 V to 4.2 V |  |  |
| Dimensions (H × W × L) | 14.5 mm × 100 mm × 301 mm |  |  |
| Weight | 882 g |  |  |
| Pack specifications | Pack 1 | Pack 2 | Pack 3 |
| Manufacturer | Hyundai Motor Company, Ltd. |  |  |
| Model | Kona Electric |  |  |
| Battery manufacturing date | June 30, 2020 | March 26, 2019 | May 14, 2019 |
| Nominal energy | 39 kWh | 64 kWh | 64 kWh |
| Nominal pack capacity | 126 Ah | 189 Ah | 189 Ah |
| Nominal pack voltage | 324 V | 352.8 V | 352.8 V |
| Topology | 90s2p | 98s3p | 98s3p |
| Number of modules | 6 | 10 | 10 |
| Connectors/HVD | 8/1 | 12/1 | 12/1 |
| Number of logical cells^a | 90 | 98 | 98 |
| Investigated electrical parameters |  |  |  |
| Test temperature | 25 °C |  |  |
| Ohmic resistance R_Ω |  |  |  |
| SOC | 50 % |  |  |
| Current | 4 A/6 A^b |  |  |
| Pulse duration | 1 ms^c |  |  |
| DC-pulse resistance R_DC,30s |  |  |  |
| SOC | 50 % |  |  |
| Current | 0.4 C |  |  |
| Pulse duration | 30 s^d |  |  |
| Capacity |  |  |  |
| Test procedure | CCCV charge and discharge^e |  |  |
| Current | 0.4 C |  |  |
| Termination | 0.02 C |  |  |
| Investigated components |  |  |  |
| Component level | R_Ω | R_DC,30s | Capacity |
| Pack | ✓ | ✓ | ✗ |
| Module | ✓ | ✗ | ✗ |
| Logical cell | ✓ | ✓ | ✓ |
| Connectors/HV disconnect | ✓ | ✗ | ✗ |

<sup>a</sup> A logical cell is a parallel connection of 2 (Pack 1) and 3 cells (Packs 2 and 3).<br><sup>b</sup> Li.plus step current amplitudes: 4 A for module connectors and measurements at the logical-cell and module levels; 6 A at the pack level.<br><sup>c</sup> Each measurement comprised 5 consecutive pulses with a step duration of 1 ms for each pulse.<br><sup>d</sup> DC-pulse resistance measured in both charge and discharge directions; 15 min rest between pulses; each measurement comprises 3 consecutive DC-pulse pairs.<br><sup>e</sup> Capacity derived from the CCCV discharge phase; only performed at the logical-cell level.

To determine the remaining capacity, ohmic resistance, and DC-pulse resistance, a 4-wire current-supply and voltage-sensing setup was used. Before disassembly, the battery packs were adjusted to 329 V, 359 V and 359 V for Packs 1–3, approximately corresponding to an SOC of 50 %. An SOC of 50 % at 25 °C was selected as a standard reference condition, as it is included in cell-level performance testing per DIN EN IEC 62660-1 and pack/system-level performance testing according to ISO 12405-4 [20,21]. After adjusting the SOC, the packs rested for at least 24 h at 25 °C within the test facility to allow thermal acclimatization and reduce transient overpotentials. This interval exceeds the 12 h thermal-conditioning period in DIN EN IEC 62660-1, but is treated as a consistent initial condition rather than proof of complete equilibrium since smaller relaxation effects may persist longer [21,41].

[Fig. 2](../assets/figure/figure-2.jpg)

**Fig. 2.** Overview of the Hyundai Kona Electric EV battery pack architectures, their subcomponents, and the numbering scheme. (a) Battery pack architecture of Pack 1. (b) Battery pack architecture of Packs 2 and 3.

**Table 2**

Key specifications of the measurement equipment used in this study.

[Table 2](../assets/table/table-2.csv)

| Property | EA PSB 11000-80 | IT M3906C-80-120 | Li.plus devices | Li.plus devices | Li.plus devices | Li.plus devices |
| --- | --- | --- | --- | --- | --- | --- |
| Level | Pack | Logical cell | Connector/HVD | Logical cell | Module | Pack |
| Voltage range | 0-1000 V | 0-80 V | ±2 mV | 2.5-5 V | 5-80 V | 80-500 V |
| Voltage resolution ΔU_res | 100 mV | 1 mV | 0.15 nV | 600 nV | ≤3 μV^a | ≤3 μV^a |
| Current range | ±80 A | ±120 A | −12.5 A | −12.5 A | −12.5 A | −12.5 A |
| Current resolution | 10 mA | 10 mA | 400 μA | 400 μA | 400 μA | 400 μA |
| Sampling rate | 10 Hz | ≤10 kHz | 20 MHz | 20 MHz | 20 MHz | 20 MHz |

<sup>a</sup> Voltage resolution refers to the AC-coupled differential voltage measurement.

First, ohmic-resistance measurements were conducted at the pack level using a pulse length of 1 ms and a current of 6 A during discharge. This corresponded to a C-rate of approximately 0.05 C for Pack 1 and 0.03 C for Packs 2 and 3. Each measurement comprised 5 consecutive discharge pulses, and at least 9 measurements were conducted for each pack, yielding a minimum of 45 individual current pulses. Subsequently, DC-pulse measurements were performed at a C-rate of 0.4 C with a pulse length of 30 s in both charge and discharge directions. A pause of 15 min was applied between the charge and discharge pulses. This sequence, consisting of one charge pulse, one discharge pulse, and one pause section, was repeated 3 times.

The packs were then disassembled into modules by removing the module connectors and the HVD. Subsequently, ohmic-resistance measurements were performed at the module level using a current of 4 A during discharge, corresponding to a C-rate of approximately 0.03 C for Pack 1 and 0.02 C for Packs 2 and 3. For each module, 2 measurements were conducted, resulting in 10 individual current pulses per module. Finally, ohmic-resistance measurements with identical settings were performed at the logical-cell level, for the individual module connectors, and for the HVDs. For the ohmic resistance, the voltage-sensing leads were placed at the respective global positive and negative terminal busbars of each pack and module, at the two ends of each detached module connector and HVD, as well as at the busbars above the terminals of each logical cell. The same pack- and logical-cell-level sensing locations were used for the DC-pulse resistance. Consequently, the detached connector and HVD measurements excluded the bolted installation interfaces, whereas the logical-cell boundaries included the tab welds and adjacent sections of the intercell busbar.

Finally, DC-pulse resistance and capacity measurements were performed at the logical-cell level. For DC-pulse resistance, the same procedure and settings as at the pack level were used. After the last pulse pair, each logical cell was first fully charged and then discharged using a constant current constant voltage (CCCV) protocol. During the CCCV procedures, a C-rate of 0.4 C and a termination current of 0.02 C within the cell voltage window of 2.5 V to 4.2 V were used. The capacity was determined by measuring the discharge throughput during the CCCV discharge step. All measurements at a given system level were completed before the corresponding components were disconnected.

### 2.2. Measurement hardware specifications

Table 2 summarizes the key specifications of the measurement equipment used in this study. These device specifications provide the technical basis for the capacity and resistance measurements introduced above. They are referred to again in Section 2.5 to contextualize measurement uncertainty and interpretability limits.

Pack-level DC-pulse resistance measurements were conducted using the PSB 11000-80 from Elektro Automatik. The device supports devices under test (DUTs) up to 1000 V, with a voltage resolution of 100 mV, a current range of ±80 A, a current resolution of 10 mA, and a sampling rate of 10 Hz. At the logical-cell level, DC-pulse resistance and capacity measurements were conducted using the IT-M3906C-80-120 from ITECH Electronic Co., Ltd. The device supports DUTs up to 80 V, providing a voltage resolution of 1 mV, a current range of ±120 A, a current resolution of 10 mA, and a sampling rate of up to 10 kHz.

Ohmic-resistance measurements were conducted using Li.plus devices equipped with application-specific measurement units. The operating range varies depending on the DUT, allowing measurements from connectors to entire packs with voltages up to 500 V. Across the measurement units, the voltage resolution is 0.15 nV for connectors, 600 nV for logical cells, and at most 3 μV for modules and packs. The current range extends to −12.5 A, with a current resolution of 400 μA, and a sampling rate of 20 MHz. As indicated in Table 2, the stated voltage resolution for modules and packs refers to the AC-coupled differential voltage measurement. Accordingly, cell-to-pack scaling of *R*<sub>DC,Δt</sub> combines measurements from the ITECH and EA devices, whereas *R*<sub>Ω</sub> is determined at all component levels using Li.plus devices based on the same measurement principle. Individual connector and HVD resistances are reported in μΩ, whereas logical-cell, module, pack, and summed non-cell resistances are reported in mΩ. Here, 1 mΩ corresponds to 1000 μΩ.

### 2.3. Measurement principles, approach, and metrics

At the logical-cell level, capacity *C* is determined from the CCCV discharge step of the reference capacity test by integrating the current over the discharge step, as given in Eq. (1).

[Eq. (1)](../assets/figure/equation-1.jpg)

Eq. (1): *C* = ∫<sub>*t*<sub>start</sub></sub><sup>*t*<sub>end</sub></sup> |*I*(*t*)| d*t*

Based on the remaining logical-cell capacity, capacity-related state of health (SOH<sub>C</sub>) is calculated according to Eq. (2). Here, *C*<sub>actual</sub> denotes the remaining capacity of the logical cell, *C*<sub>N</sub> the nominal capacity of a single cell, and *n*<sub>cells</sub> the number of parallel-connected cells forming the logical cell. This normalization enables comparison of logical-cell SOH<sub>C</sub> across the 2p and 3p pack architectures.

[Eq. (2)](../assets/figure/equation-2.jpg)

Eq. (2): SOH<sub>C</sub> = *C*<sub>actual</sub> / (*C*<sub>N</sub> ⋅ *n*<sub>cells</sub>)

All resistances, including those of the pack and its subcomponents, are determined using Ohm’s law as given in Eq. (3). The DC-pulse resistance is defined as the ratio of the voltage and current differences between the start of the current transient and the selected evaluation time Δ*t*.

[Eq. (3)](../assets/figure/equation-3.jpg)

Eq. (3): *R*<sub>DC,Δt</sub> = Δ*U* / Δ*I* = (*u*(*t*<sub>0</sub> + Δ*t*) − *u*(*t*<sub>0</sub>)) / (*i*(*t*<sub>0</sub> + Δ*t*) − *i*(*t*<sub>0</sub>))

In this study, *R*<sub>DC,Δt</sub> is evaluated at Δ*t*=1 s, 10 s and 30 s. The selection follows Wassiliadis et al. [1], who evaluated DC-pulse resistance at the same times within 30 s pulses, and is supported by related timings in performance standards. DIN EN IEC 62660-1 uses 10 s charge and discharge pulses with a 1 s measurement interval, whereas ISO 12405-4 includes 10 s resistance values in both directions and a 30 s discharge-resistance value for high-energy packs and systems [20,21]. The 1 s value contains the ohmic contribution together with fast interfacial polarization, while the 10 s and 30 s values contain increasing contributions from slower concentration and diffusion processes [38].

The Li.plus device enables the determination of the early-time ohmic resistance using a low-current pulse in the time domain, together with high-temporal-resolution measurements of both the terminal voltage and the applied current [39]. From these signals, the ohmic resistance, the inductance, and other ECM parameters are determined with an analytical algorithm. An overview of the current profile, the corresponding voltage response, and the conventional 30 s DC-pulse is shown in Fig. 3.

In Fig. 3 (a), the applied current and the corresponding terminal-voltage response of the ohmic-resistance measurement are shown for Module 1 of Pack 2 without additional preprocessing or smoothing. The current pulse starts from a constant current (CC) offset of −300 mA. After 175 μs, the current decreases linearly to −4 A within 50 μs, is held for 450 μs, and then increases linearly within 50 μs back to the initial offset current without overshoot. The overall pulse duration is 1 ms. Pulse duration, rise and fall times, current amplitude, and the number of consecutive repetitions can be adjusted by the user.

In addition to the measured current and terminal-voltage response, Fig. 3 (a) includes the simulated voltage response of a simplified ECM comprising an ohmic resistance *R*<sub>Ω</sub> and an inductance *L*. Fig. 3 (b) shows the voltage contribution attributable to the ohmic resistance *R*<sub>Ω</sub>, resulting in a value of 3.95 mΩ and a constant overpotential of 15.88 mV once the current has stabilized in its CC phase. Fig. 3 (c) shows the voltage contribution attributable to the inductance *L*. During the linear current ramp, d*I*∕d*t* is approximately constant. Consequently, the inductive contribution *u*<sub>L</sub>= *L* d*I*∕d*t* is expected to be constant during the ramp and decays once the CC phase is reached. For the example shown, the inductive contribution is approximately 60 mV, corresponding to an inductance of about 0.7 μH.

The remaining discrepancy between the measured terminal voltage response and the simplified *R*<sub>Ω</sub> + *L* model is shown in Fig. 3 (d). This voltage residual results in an RMSE of 2.25 mV during the 1 ms pulse window. This error is mainly caused by high-frequency electromagnetic effects and current distribution phenomena [42], such as the skin effect and current crowding, with minor contributions from the fixture and measurement chain. Consequently, the patented pulse method [39] provides an analytical framework for interpreting the early-time voltage response.

Following this method, the characteristic voltage extrema can be used to identify the transition from inductive decay to the early-time ohmic response. For the present dataset, Δ*t*= 400 μs was selected as the evaluation time within this early-time response. At this evaluation time, the dominant inductive contribution had largely decayed across the investigated component levels. At the same time, the slower overpotential contributions from the solid electrolyte interface (SEI) and charge-transfer processes, commonly represented by a resistor-capacitor (RC) element, were expected to affect the terminal voltage only to a limited extent [42]. Accordingly, we define the ohmic resistance as the early-time special case of Eq. (3) described in Eq. (4).

[Eq. (4)](../assets/figure/equation-4.jpg)

Eq. (4): *R*<sub>Ω</sub> = *R*<sub>DC,Δt=400μs</sub> = Δ*U* / Δ*I* |<sub>Δt=400μs</sub>

To evaluate the robustness of the selected evaluation time, the resistance was additionally determined at Δ*t*= 200 μs and Δ*t*= 450 μs using the same processing procedure for all logical-cell, module, and pack measurements. Relative to the values at 400 μs, evaluation at 450 μs results in mean absolute deviations of 0.38 %, 0.42 %, and 0.30 % at the logical-cell, module, and pack levels, respectively. For the logical-cell and module populations, 95 % of the absolute deviations remain below 0.92 % and 0.93 %, respectively, while the maximum deviation at the pack level is 0.43 %. In comparison, evaluation at 200 μs results in larger mean absolute deviations of 2.92 %, 0.95 %, and 0.91 %, respectively. The substantially lower sensitivity between 400 μs and 450 μs supports selecting 400 μs as a robust early-time evaluation point under the applied measurement protocol. The corresponding evaluation-time distributions for all three packs and component levels are provided in Fig. A.7.

The application of this low-current pulse profile at the different component levels is shown in Fig. 3 (e)–(g) for the pack, module, and logical-cell levels, respectively. A maximum current of 6 A was used at the pack level and 4 A at the module and logical-cell levels. The black crosses indicate the evaluation points used for the determination of the ohmic resistance *R*<sub>Ω</sub>. For comparison, Fig. 3 (h) shows a 30 s DC-pulse at the logical-cell level during discharge, measured with the IT-M3906C-80-120 at a C-rate of 0.4 C. Together, Fig. 3 (e)–(h) illustrate the consistent use of the resistance definitions across component levels and distinguish the early-time determination of *R*<sub>Ω</sub> from the conventional determination of *R*<sub>DC,Δt</sub>.

[Fig. 3](../assets/figure/figure-3.jpg)

**Fig. 3.** Overview of the low-current pulse profile and the 30 s DC-pulse protocol used to determine the early-time ohmic resistance *R*<sub>Ω</sub> and DC-pulse resistance *R*<sub>DC,Δt</sub> of battery systems across different component levels. (a) Low-current excitation and corresponding terminal-voltage response for Module 1 of Pack 2, including the simulated voltage response obtained from an equivalent circuit comprising a resistance *R*<sub>Ω</sub> and an inductance *L*. (b)–(c) Voltage contributions attributable solely to *R*<sub>Ω</sub> and *L*, respectively. (d) Residual voltage that is not captured by the *R*<sub>Ω</sub>–*L* model, resulting in a RMSE of 2.25 mV over the 1 ms pulse duration. For clarity, only the first 600 μs are shown in (a)–(d). (e)–(g) Voltage and current trajectories of the low-current pulse profile applied at the pack, module, and logical-cell levels, respectively. (h) Example of a 30 s DC-pulse for logical cell 1 of Module 1 of Pack 2 during discharge.

Based on the capacity and resistance definitions above, the subsequent analysis quantifies the relative dispersion and homogeneity of these metrics across the different components of each pack. To characterize the dispersion of a metric *x*, for example *C*, *R*<sub>Ω</sub>, or *R*<sub>DC,Δt</sub>, across a population of components, we use the CoV as given in Eq. (5).

[Eq. (5)](../assets/figure/equation-5.jpg)

Eq. (5): CoV(*x*) = *s* / *x̄* = √((1/(*n*−1)) Σ<sub>i=1</sub><sup>n</sup> (*x*<sub>i</sub> − *x̄*)<sup>2</sup>) / ((1/*n*) Σ<sub>i=1</sub><sup>n</sup> *x*<sub>i</sub>)

Here, *x*<sub>i</sub> denotes the value of metric *x* for component *i* (*i*= 1, … , *n*), *x̄* is the sample mean of *x*, *s* is the sample standard deviation including Bessel’s correction, and *n* is the number of components considered. The CoV captures the overall relative spread of a metric within the investigated component population.

In addition, the homogeneity of capacity and resistance is evaluated at the logical-cell and module levels using the SOHo indicators in Eq. (6), as proposed in the context of centralized and distributed pack diagnostics [3]. In contrast to the CoV, these indicators emphasize the maximum pairwise deviation within the population under consideration and therefore complement the statistical dispersion analysis with a worst-case-oriented measure of homogeneity.

[Eq. (6)](../assets/figure/equation-6.jpg)

Eq. (6): SOHo<sub>x</sub> ≜ 1 − max<sub>i≠j</sub>{|*x*<sub>i</sub> − *x*<sub>j</sub>|} / max<sub>i</sub>{*x*<sub>i</sub>}, *x* ∈ {*C*, *R*}

### 2.4. Resistance additivity investigation

To assess resistance additivity across component levels, the calculated resistance *R*<sub>x,calc</sub> is compared with the corresponding measured resistance *R*<sub>x,meas</sub> for each resistance metric *x* and scaling path. The calculated resistance is derived by adding all measured lower-level contributions along the corresponding series path. In this study, three scaling paths are analyzed: cell-to-pack for all resistance metrics, and cell-to-module and module-to-pack for *R*<sub>Ω</sub>. Hereafter, the terms cell-to-pack and cell-to-module refer to scaling from the logical-cell level. For each scaling path, the calculated resistance *R*<sub>x,calc</sub>, the absolute residual Δ*R*<sub>x</sub>, and the relative residual *ε*<sub>Rx</sub> are defined as

[Eqs. (7a)–(7c)](../assets/figure/equations-7a-to-7c.jpg)

Eq. (7a): *R*<sub>x,calc</sub> = Σ<sub>j∈ℛ<sub>p</sub></sub> *R*<sub>x,j</sub><br>Eq. (7b): Δ*R*<sub>x</sub> = *R*<sub>x,calc</sub> − *R*<sub>x,meas</sub><br>Eq. (7c): *ϵ*<sub>R<sub>x</sub></sub> = Δ*R*<sub>x</sub> / *R*<sub>x,meas</sub>

Here, ℛ<sub>p</sub> denotes the set of all component contributions included in the path. For the cell-to-pack and module-to-pack paths, ℛ<sub>p</sub> contains non-cell contributions and all logical-cell or module resistances. For the cell-to-module path, only the logical-cell resistances are considered.

### 2.5. Measurement uncertainty

We evaluate measurement uncertainty according to the Guide to the expression of uncertainty in measurement (GUM) [43]. Type A contributions are derived from repeated measurements, while Type B contributions come from prior information, for example, the finite resolution of a measurement device. For a measurand *X* with *n* repeated measurements *X*<sub>j</sub>, the mean *X̄*, the sample standard deviation *s*<sub>X</sub>, and the Type A standard uncertainty of the mean *u*<sub>A</sub>(*X̄*) are given in Eq. (8).

[Eqs. (8a)–(8c)](../assets/figure/equations-8a-to-8c.jpg)

Eq. (8a): *X̄* = (1/*n*) Σ<sub>j=1</sub><sup>n</sup> *X*<sub>j</sub><br>Eq. (8b): *s*<sub>X</sub> = √((1/(*n*−1)) Σ<sub>j=1</sub><sup>n</sup> (*X*<sub>j</sub> − *X̄*)<sup>2</sup>)<br>Eq. (8c): *u*<sub>A</sub>(*X̄*) = *s*<sub>X</sub> / √*n*

For DC-pulse resistance, 6 resistances are available for each logical cell and pack. For ohmic resistance, 5, 10, and 45 resistances are available at the logical-cell, module, and pack levels, respectively. The expanded uncertainty is expressed as *U*= *k*⋅*u*, where *u* denotes the standard uncertainty and *k* is the coverage factor. For the repeated measurements considered, *k* is derived from the two-sided Student-*t* distribution. Assuming that the repeated measurements are independent and approximately normally distributed, the interval *R̄*<sub>x</sub>± *U* is reported with a confidence level of 95 %. For the resistance measurements in this study, *k* ranges from 2.78 for *n*= 5 to 2.02 for *n*= 45. Thus, smaller sample sizes require larger coverage factors to reach the same confidence level, and *k* approaches the value of 2 as *n* increases.

The propagation of uncertainty from several independent inputs to a derived quantity is given in Eq. (9).

[Eq. (9)](../assets/figure/equation-9.jpg)

Eq. (9): *u*<sub>c</sub>(*Y*) = √(Σ<sub>i=1</sub><sup>m</sup> (∂*f*/∂*X*<sub>i</sub>)<sup>2</sup> *u*(*X*<sub>i</sub>)<sup>2</sup>), *Y* = *f*(*X*<sub>1</sub>, …, *X*<sub>m</sub>)

We apply uncertainty propagation when scaling the resistance from the logical-cell level to the module or pack level. First, we derive the propagated standard uncertainty of the calculated pack resistance, *u*(*R*<sub>x,pack,calc</sub>), and the standard uncertainty of the measured pack resistance, *u*(*R*<sub>x,pack,meas</sub>). These two uncertainties are then propagated to obtain the uncertainty of the residual *u*(Δ*R*<sub>x</sub>). Finally, the resulting standard uncertainty is multiplied by the coverage factor *k*.

In addition, for DC-pulse resistance scaling, a non-negligible Type B standard uncertainty has to be considered since the PSB 11000-80 voltage resolution Δ*U*<sub>res</sub> is only 0.1 V. The standard uncertainty *u*<sub>q</sub>(*U*[V]) for one voltage record within the uniform interval ±Δ*U*<sub>res</sub>∕2 is given in Eq. (10).

[Eq. (10)](../assets/figure/equation-10.jpg)

Eq. (10): *u*<sub>q</sub>(*U*[V]) = Δ*U*<sub>res</sub>[V] / √12

Since the resistance is calculated from the difference of two voltage measurements, the propagated uncertainty of the voltage difference *u*<sub>q</sub>(Δ*U*[V]) is given by Eq. (11).

[Eq. (11)](../assets/figure/equation-11.jpg)

Eq. (11): *u*<sub>q</sub>(Δ*U*[V]) = √((Δ*U*<sub>res</sub>[V]/√12)<sup>2</sup> + (Δ*U*<sub>res</sub>[V]/√12)<sup>2</sup>) = Δ*U*<sub>res</sub>[V] / √6

Using a DC-pulse current of 50 A for Pack 1 and 75 A for Packs 2 and 3, the relative contribution of current resolution to *u*<sub>B</sub>(*R*<sub>DC,Δt</sub>) is only 0.005 % to 0.008 % and is therefore neglected. Thus, the Type B propagated uncertainty for the DC-pulse resistance can be expressed as in Eq. (12).

[Eq. (12)](../assets/figure/equation-12.jpg)

Eq. (12): *u*<sub>B</sub>(*R*<sub>DC,Δt</sub>) = √((∂*R*<sub>DC,Δt</sub>/∂Δ*U*[V])<sup>2</sup> ⋅ *u*<sub>q</sub>(Δ*U*[V])<sup>2</sup> + (∂*R*<sub>DC,Δt</sub>/∂*I*[A])<sup>2</sup> ⋅ *u*<sub>q</sub>(Δ*I*[A])<sup>2</sup>) ≈ *u*<sub>q</sub>(Δ*U*[V]) / *I* = Δ*U*<sub>res</sub>[V] / (*I*√6)

When deriving the propagated uncertainty of the residual between scaled and measured pack DC-pulse resistance, the independent Type A and Type B contributions of the measured DC-pulse resistance are combined following Eq. (13).

[Eq. (13)](../assets/figure/equation-13.jpg)

Eq. (13): *u*<sub>c</sub>(*R̄*<sub>DC,Δt,meas</sub>) = √(*u*<sub>A</sub>(*R̄*<sub>DC,Δt,meas</sub>)<sup>2</sup> + *u*<sub>B</sub>(*R̄*<sub>DC,Δt,meas</sub>)<sup>2</sup>)

The combined expanded uncertainty is then obtained as *U*<sub>c</sub>= *k*⋅ *u*<sub>c</sub>, using the Student-*t* coverage factor for the 6 repeated DC-pulse observations. The resulting expanded uncertainties for all resistance metrics and component levels are summarized in Table 4 and serve as the interpretability limits for the dispersion analysis in Section 4.1.

## 3. Results

This section presents the voltages of the logical cells after adjusting the SOC to ensure that all determined resistances can be compared on a common basis. Following this, we present the measurement results of the remaining capacities and ohmic resistances of the 3 field-aged EV battery packs across all component levels. A broader interpretation of the results, both within and across the packs, is discussed in Section 4.

### 3.1. Voltage comparison across the packs

To establish a basis for comparing resistance results within and across the packs, the logical-cell voltages after SOC adjustment and a 24 h rest period are evaluated. Table 3 summarizes the voltage statistics of the logical cells within each pack.

**Table 3**

Voltage statistics after SOC adjustment to 50 % and a subsequent 24 h rest period. Topology denotes the pack architecture, *Ū* the mean voltage of the logical cells within each pack, *s*<sub>U</sub> the standard deviation, *U*<sub>min</sub> and *U*<sub>max</sub> the minimum and maximum, Δ*U* the overall spread, and CoV the relative voltage dispersion.

[Table 3](../assets/table/table-3.csv)

|  | Pack 1 | Pack 2 | Pack 3 |
| --- | --- | --- | --- |
| U_pack | 329.7 V | 359.4 V | 359.6 V |
| Topology | 90s2p | 98s3p | 98s3p |
| Logical-cell level |  |  |  |
| Ū | 3.663 V | 3.667 V | 3.669 V |
| s_U | 1.1 mV | 0.8 mV | 0.9 mV |
| U_max | 3.665 V | 3.668 V | 3.672 V |
| U_min | 3.653 V | 3.661 V | 3.667 V |
| ΔU | 12 mV | 8 mV | 4 mV |
| CoV | 0.03 % | 0.02 % | 0.02 % |

At the pack level, the voltages are 329.7 V, 359.4 V, and 359.6 V for Packs 1–3, with Packs 2 and 3 showing nearly identical voltages after SOC adjustment. More importantly, the mean logical-cell voltages are 3.663 V, 3.667 V, and 3.669 V, while the corresponding spreads remain limited to 12 mV, 8 mV, and 4 mV. As a result, the associated CoVs remain at or below 0.03 %. These values indicate highly uniform voltages both within and across the packs. The observed logical-cell voltages of 3.66 V to 3.67 V are consistent with a mid-SOC regime, in which the resistance can be assumed to be approximately constant [27,28,37]. Thus, resistance results can be compared on a common SOC basis.

### 3.2. Component-resolved overview of capacity and ohmic resistance across the packs

Fig. 4 presents the component-resolved results of Pack 1. At the pack level, Fig. 4 (a) shows a mean ohmic resistance of 51.19 mΩ, based on 45 individual pulses and a mean logical-cell capacity of 120.3 Ah. In Fig. 4 (b), the ohmic resistances of the individual module connectors and the HVD are presented. Their total resistance is 1.46 mΩ, corresponding to 2.9 % of the measured pack resistance. The largest individual contribution is connector C<sub>45</sub> with 566.58 μΩ, followed by the HVD with 487.79 μΩ. The grouped short connectors C<sub>12,34,56</sub> each show the lowest ohmic resistance at 18.55 μΩ. This resistance distribution reflects the electrical path length along the current path, as shown in Fig. 2.

[Fig. 4](../assets/figure/figure-4.jpg)

**Fig. 4.** Component-resolved overview of capacity and ohmic resistance from the pack to logical-cell level for Pack 1. (a) Repeated pack-level ohmic-resistance measurements and the distribution of measured logical-cell capacities. (b) Ohmic resistances of the individual module connectors and the HVD. (c) Repeated module-level ohmic-resistance measurements. (d) Logical-cell capacities grouped by module. (e) and (f) Ohmic resistances and capacities of all 90 logical cells, with logical-cell indexing repeated within each module block. Outliers are identified using the 1.5 × IQR criterion and retained in all calculations.

At the module level, shown in Fig. 4 (c) and (d), the mean ohmic resistances range from 8.25 mΩ to 8.32 mΩ, adding up to 49.73 mΩ, while the capacity means range from 120.2 Ah to 120.4 Ah. At the logical-cell level, shown in Fig. 4 (e) and (f), the ohmic resistances range from 0.544 mΩ to 0.575 mΩ, adding up to 50.42 mΩ. The capacities range from 119.90 Ah to 120.90 Ah, with a mean value of 120.35 Ah. The minimum capacity of 119.90 Ah occurs 3 times, namely in Modules 1, 3, and 4 at logical cells 3, 1, and 6, respectively. These capacity results correspond to a SOH<sub>C</sub> spread of 0.79 % and a CoV of 0.15 %. Overall, Fig. 4 does not indicate a distinct module block or logical-cell position that deviates from the remaining cells.

Figs. 5 and 6 present the component-resolved results of Packs 2 and 3. The mean pack-level ohmic resistances are 40.83 mΩ for Pack 2 and 40.01 mΩ for Pack 3, based on 10 and 14 repeated measurements, respectively. The corresponding mean logical-cell capacities are 179.1 Ah and 179.8 Ah. The total contributions from connectors and the HVD are 1.73 mΩ in both packs, corresponding to 4.2 % of the measured pack resistance for Pack 2 and 4.3 % for Pack 3. Using Pack 2 as an example, the largest connector contribution is C<sub>89</sub> with 509.07 μΩ, followed by the HVD with 441.38 μΩ, while the grouped short connectors C<sub>12,34,56,78,910</sub> are at 30.93 μΩ. In Pack 2, the modules containing 10 logical cells have resistances ranging from 3.96 mΩ to 4.04 mΩ. In Pack 3, the range is from 3.92 mΩ to 3.96 mΩ. In Pack 2, Modules 4 and 6, which each contain 9 logical cells, are both at 3.56 mΩ, whereas in Pack 3 their ohmic resistances are 3.55 mΩ and 3.53 mΩ, respectively. The offset between the modules containing 10 and 9 logical cells is approximately 0.4 mΩ in both packs, which closely matches the mean logical-cell ohmic resistances of 0.404 mΩ and 0.396 mΩ for Packs 2 and 3. The summed module ohmic resistances are 39.15 mΩ for Pack 2 and 38.62 mΩ for Pack 3.

At the module level, the capacity means range from 178.4 Ah to 179.6 Ah in Pack 2 and from 179.7 Ah to 180.1 Ah in Pack 3. At the logical-cell level, the ohmic resistances range from 0.375 mΩ to 0.423 mΩ in Pack 2 and from 0.355 mΩ to 0.412 mΩ in Pack 3, with a summed resistance of 39.61 mΩ and 38.84 mΩ, respectively. Notably, the last logical cell in a module consistently exhibits lower ohmic resistance than the preceding cells. This systematic difference prompted a separate evaluation of the two within-module connector types. Their ohmic resistances are 51 μΩ and 29 μΩ, corresponding to a difference of about 22 μΩ. Adding this difference to the resistance of the final logical cell brings its value into the same range as the previous logical cells in the same module.

[Fig. 5](../assets/figure/figure-5.jpg)

**Fig. 5.** Component-resolved overview of capacity and ohmic resistance from the pack to the logical-cell level for Pack 2. (a) Repeated pack-level ohmic-resistance measurements and the distribution of measured logical-cell capacities. (b) Ohmic resistances of the individual module connectors and the HVD. (c) and (d) Repeated module-level ohmic-resistance measurements for modules containing 10 and 9 logical cells, respectively. (e) Logical-cell capacities grouped by module. (f) and (g) Ohmic resistances and capacities of all 98 logical cells, with logical-cell indexing repeated within each module block. Outliers are identified using the 1.5 × IQR criterion and retained in all calculations.

The logical-cell capacities range from 175.4 Ah to 180.5 Ah in Pack 2 and from 178.1 Ah to 180.8 Ah in Pack 3. For Pack 2, the two limiting logical cells are logical cell 10 in Module 1 and logical cell 10 in Module 10. For Pack 3, the limiting logical cell is located at logical cell 1 in Module 9. These results correspond to a ΔSOH<sub>C</sub> of 2.70 % and a CoV of 0.41 % for Pack 2, compared with 1.43 % and 0.19 % for Pack 3. Overall, Pack 2 shows a lower mean SOH<sub>C</sub>, lower limiting capacities, and higher ohmic resistances than Pack 3.

## 4. Discussion

### 4.1. Uncertainty and interpretability of resistance dispersion

The resistance results in Section 3 can only be interpreted by comparing the observed differences with the specific metric and component uncertainties derived in Section 2.5. As shown in Section 3.1, the voltage was highly uniform within each pack and closely matched between Packs 2 and 3 before the resistance measurements, reducing the likelihood that the observed variations reflect differences in SOC. To decide whether the observed module-to-module or cell-to-cell spreads reflect heterogeneity beyond measurement uncertainty, we compare each CoV with the maximum relative expanded uncertainty within the corresponding population. This conservative approach uses the highest uncertainty as representative for the entire group. When the ratio of the CoV to the relative expanded uncertainty rel. *U* exceeds 1, the observed heterogeneity is considered resolved. In contrast, ratios of CoV∕rel. *U* below 1 imply that the observed dispersion cannot be distinguished from the determined uncertainty. A one-sided *F*-test confirms the same classification. Since both metrics lead to consistent conclusions across all module and logical-cell comparisons, the following discussion reports the CoV∕rel. *U* ratio as the primary interpretability metric. Table 4 summarizes the expanded uncertainties determined.

[Fig. 6](../assets/figure/figure-6.jpg)

**Fig. 6.** Component-resolved overview of capacity and ohmic resistance from the pack to the logical-cell level for Pack 3. (a) Repeated pack-level ohmic-resistance measurements and the distribution of measured logical-cell capacities. (b) Ohmic resistances of the individual module connectors and the HVD. (c) and (d) Repeated module-level ohmic-resistance measurements for modules containing 10 and 9 logical cells, respectively. (e) Logical-cell capacities grouped by module. (f) and (g) Ohmic resistances and capacities of all 98 logical cells, with logical-cell indexing repeated within each module block. Outliers are identified using the 1.5 × IQR criterion and retained in all calculations.

At the pack level, the expanded repeatability uncertainty remains low at 10 μΩ to 15 μΩ across all 3 packs, corresponding to a relative uncertainty of 0.03 %. The differences at the pack level reported in Section 3.2 are substantially larger than the determined uncertainties. For the only architecturally comparable pair, Packs 2 and 3, the difference in *R*<sub>Ω</sub> is 0.83 mΩ, which exceeds the propagated expanded uncertainty by a factor of about 50. DC-pulse resistance *R*<sub>DC,Δt</sub> is less favorable since the PSB 11000-80 voltage resolution dominates the propagated uncertainty. The combined expanded uncertainty *U*<sub>c</sub>, which accounts for both the resolution and repeatability contributions, ranges from 1.51 mΩ to 2.27 mΩ across the 9 pack cases, corresponding to relative uncertainties of 1.9 % to 3.3 %. Packs 2 and 3 differ by 3.81 mΩ at *R*<sub>DC,10 s</sub>, which exceeds the propagated expanded uncertainty *U*<sub>Δ</sub>(*U*<sub>c,P2</sub>, *U*<sub>c,P3</sub>) = 2.18 mΩ by a factor of about 1.7.

At the module level, we assess the dispersion of ohmic resistance *R*<sub>Ω</sub> only within modules containing 10 logical cells. The CoVs range from 0.25 % to 0.85 %, while the conservative relative expanded uncertainty ranges from 0.22 % to 0.61 %. This results in CoV∕rel. *U* ratios of 1.4, 2.0, and 0.4 for Packs 1–3, respectively. Thus, module-to-module variation is resolved for Packs 1 and 2, while the modules of Pack 3 cannot be distinguished within the determined uncertainty. At the logical-cell level, the CoV ranges from 1.45 % to 2.39 %, while the conservative relative expanded uncertainty ranges from 0.76 % to 0.88 %. This results in CoV∕rel. *U* ratios of 1.9, 2.6, and 2.7. All ratios exceed 1, showing that the measured cell-to-cell dispersion in *R*<sub>Ω</sub> is resolved in all 3 packs. At the same time, the logical-cell ohmic resistances remain closely clustered around their respective means.

Heterogeneity is not resolved for DC-pulse resistance under the same conservative criterion. For Packs 1–3, the resulting CoV∕rel. *U* ratios are 0.14, 0.09, and 0.43. The large conservative uncertainty is mainly driven by individual measurements with high dispersion. In Pack 2, for example, the worst-case repeatability standard deviation at 10 s is 0.263 mΩ, while the median standard deviation across all cells in the same pack is only 0.013 mΩ. If these median expanded uncertainties were used instead, the CoV∕rel. *U* ratios would increase to 2.7, 1.9, and 3.4, which would indicate resolved dispersion. We retain the conservative criterion to preserve comparability across resistance metrics and measurement devices. Under this criterion, logical-cell DC-pulse resistance should be regarded as unresolved rather than homogeneous. Since *R*<sub>Ω</sub> already resolves logical-cell dispersion in all 3 packs, the limitation lies in the precision of the DC-pulse measurement rather than in the absence of underlying heterogeneity.

**Table 4**

Uncertainties of ohmic and DC-pulse resistance across component levels. For pack-level *R*<sub>DC,Δt</sub>, *U*<sub>c</sub> combines repeatability and voltage quantization uncertainty, while *u*<sub>q</sub> describes the standard voltage quantization uncertainty alone.

[Table 4](../assets/table/table-4.csv)

| Resistance | Level | Quantity | Pack 1 | Pack 2 | Pack 3 |
| --- | --- | --- | --- | --- | --- |
| Ohmic resistance R_Ω | Pack | R_Ω ± U/mΩ | 51.188 ± 0.015 | 40.832 ± 0.014 | 39.999 ± 0.010 |
| Ohmic resistance R_Ω | Module^a | R_Ω,mean ± U/mΩ^b | 8.288 ± 0.018 | 4.003 ± 0.017 | 3.939 ± 0.024 |
| Ohmic resistance R_Ω | Module^a | ΔR_Ω/mΩ | 0.066 | 0.076 | 0.035 |
| Ohmic resistance R_Ω | Module^a | CoV(R_Ω)/% | 0.30 | 0.85 | 0.25 |
| Ohmic resistance R_Ω | Module^a | rel. U(R_Ω)/%^b | 0.22 | 0.42 | 0.61 |
| Ohmic resistance R_Ω | Module^a | CoV/rel. U^b | 1.4 | 2.0 | 0.4 |
| Ohmic resistance R_Ω | Log. cell | R_Ω,mean ± U/mΩ^b | 0.560 ± 0.0043 | 0.404 ± 0.0035 | 0.396 ± 0.0035 |
| Ohmic resistance R_Ω | Log. cell | ΔR_Ω/mΩ | 0.032 | 0.048 | 0.057 |
| Ohmic resistance R_Ω | Log. cell | CoV(R_Ω)/% | 1.45 | 2.32 | 2.39 |
| Ohmic resistance R_Ω | Log. cell | rel. U(R_Ω)/%^b | 0.76 | 0.88 | 0.88 |
| Ohmic resistance R_Ω | Log. cell | CoV/rel. U^b | 1.9 | 2.6 | 2.7 |
| DC-pulse resistance R_DC,Δt | Pack | u_q(R_DC)/mΩ | 0.82 | 0.54 | 0.54 |
| DC-pulse resistance R_DC,Δt | Pack | R_DC,1s ± U_c/mΩ | 68.32 ± 2.27 | 59.03 ± 1.58 | 55.77 ± 1.51 |
| DC-pulse resistance R_DC,Δt | Pack | R_DC,10s ± U_c/mΩ | 81.98 ± 2.10 | 68.91 ± 1.58 | 65.10 ± 1.51 |
| DC-pulse resistance R_DC,Δt | Pack | R_DC,30s ± U_c/mΩ | 95.98 ± 2.10 | 80.76 ± 1.53 | 76.66 ± 1.58 |
| DC-pulse resistance R_DC,Δt | Log. cell^c | R_DC,10s,mean ± U/mΩ^b | 0.951 ± 0.143 | 0.669 ± 0.276 | 0.693 ± 0.039 |
| DC-pulse resistance R_DC,Δt | Log. cell^c | ΔR_DC,10s/mΩ | 0.088 | 0.184 | 0.088 |
| DC-pulse resistance R_DC,Δt | Log. cell^c | CoV(R_DC,10s)/% | 2.07 | 3.80 | 2.40 |
| DC-pulse resistance R_DC,Δt | Log. cell^c | rel. U(R_DC,10s)/%^b | 15.06 | 41.29 | 5.57 |
| DC-pulse resistance R_DC,Δt | Log. cell^c | CoV/rel. U^b | 0.14 | 0.09 | 0.43 |

<sup>a</sup> Comparable module groups only. Pack 1: all modules. Packs 2 and 3: only modules containing 10 logical cells.<br><sup>b</sup> Conservative expanded uncertainty: largest expanded uncertainty observed across all modules or logical cells within each pack.<br><sup>c</sup> Only Δ*t*= 10 s is shown. The results for Δ*t*= 1 s and 30 s follow the same pattern for all packs.

This limitation does not imply that the instrumentation is generally unsuitable. At the logical-cell level, the classification results are based on the conservative worst-case criterion, rather than the device resolution of 1 mV. At the pack level, the 100 mV voltage resolution of the PSB 11000-80 represents a known constraint of test equipment operating above 350 V. The analysis quantifies this effect and defines the resolution required to resolve DC-pulse dispersion at the pack level.

### 4.2. Cross-pack synthesis of capacity and resistance dispersion

Table 5 summarizes the dispersion metrics of the 3 packs, with nominal capacities of 126 Ah for Pack 1 and 189 Ah for Packs 2 and 3. The mean logical-cell capacities are 120.3 Ah, 179.1 Ah and 179.8 Ah for Packs 1–3, with absolute spreads of 1.0 Ah, 5.1 Ah and 2.7 Ah, respectively. The corresponding CoVs at the logical-cell level are 0.15 %, 0.41 % and 0.19 %. A similar ranking is observed at the module level, where the CoVs are 0.11 %, 0.76 % and 0.27 %. Thus, Pack 2 exhibits greater capacity dispersion than the other two packs.

To compare the different topologies on a common basis, the measured logical-cell capacities are normalized to SOH<sub>C</sub> by their respective nominal capacities. The resulting mean SOH<sub>C</sub> values are 95.5 %, 94.8 % and 95.1 %, corresponding to an absolute spread of only 0.7 % across the 3 packs. This spread indicates comparable average aging states when characterized 5 to 6 years after manufacturing. Since pack-level capacity was not measured directly, the minimum logical-cell capacity is used to estimate the pack capacity under the voltage window applied to the logical cells. The resulting SOH<sub>C,log.,cell,min</sub> estimates are 95.2 %, 92.8 % and 94.2 % for Packs 1–3, corresponding to within-pack spreads of 0.79 %, 2.70 % and 1.43 %. These capacity-based estimates exceed the 80 % Euro 7 threshold by at least 12 percentage points. Euro 7, however, defines vehicle-level battery durability in terms of usable energy, whereas the present study measures capacity at the logical-cell level after teardown. The capacity proxy does not account for voltage-dependent energy differences and therefore represents an upper bound on energy retention. Preger et al. [44] showed across twelve datasets that the energy-to-capacity decrease ratio drops from about 99.5 % in early life to about 92 % in late life. Applying this conservative late-life ratio to the present minimum logical-cell values yields estimated energy-related state of health (SOH<sub>E</sub>) values of 87.6 %, 85.4 % and 86.7 %, which still exceed the 80 % threshold. This comparison provides numerical context only and does not constitute a formal Euro 7 compliance assessment. The corresponding SOHo values from Eq. (6) are 99.1 %, 97.2 % and 98.5 %. Thus, even the minimum-capacity logical cell deviates by less than 3 % from the population maximum in all 3 packs.

At the module level, *R*<sub>Ω</sub> indicates a largely homogeneous aging pattern across all 3 packs, consistent with the capacity observations. The resulting resistance-related homogeneity indicator (SOHo<sub>R</sub>) values for Pack 1 to Pack 3 range from 98.1 % to 99.2 %. Still, despite this homogeneous picture across the modules within each pack, dispersion can be resolved for Packs 1 and 2 since the CoV∕rel. *U* proxy introduced in Section 4.1 exceeds 1. This is not the case for Pack 3, where the absolute spread is too small to exceed the conservative uncertainty. Even in the resolved cases, the ratios remain close to 1, while module-level CoV(*R*<sub>Ω</sub>) stays low at 0.25 % to 0.85 %.

At the logical-cell level, ohmic resistance dispersion is resolved in all 3 packs, with CoV(*R*<sub>Ω</sub>) from 1.45 % to 2.39 %. Thus, the logical cells can be differentiated by *R*<sub>Ω</sub>, but remain tightly grouped. Notably, Pack 2 shows the highest capacity CoV, whereas Pack 3 shows the highest ohmic-resistance CoV. Thus, capacity and ohmic-resistance heterogeneity do not follow the same pack ranking. The ratios CoV(*R*<sub>Ω</sub>)∕CoV(*C*) range from 5.7 to 12.6, while the SOHo<sub>R</sub> values are 4.7 to 12.4 percentage points lower than the capacity-related homogeneity indicator (SOHo<sub>C</sub>) values. Ohmic resistance is therefore more sensitive than capacity, even though the overall aging pattern remains comparatively uniform. Previous cell studies on NMC, NCA, and LFP cells indicate that resistance dispersion typically exceeds capacity dispersion by a ratio of 2.3 to 8.5, although these literature values reflect BOL manufacturing variation rather than field-aged pack populations [45–47].

**Table 5**

Component-resolved dispersion and conservative uncertainty summary for capacity and resistance across the 3 field-aged battery packs. The module-level values represent the average or spread of per-module measurements, while values at the logical-cell level are calculated across all logical cells.

[Table 5](../assets/table/table-5.csv)

| Section | Quantity | Pack 1 | Pack 2 | Pack 3 |
| --- | --- | --- | --- | --- |
|  | Topology | 90s2p | 98s3p | 98s3p |
| Capacity C | C̄_log.cell/Ah | 120.35 | 179.11 | 179.83 |
| Capacity C | ΔC_module/Ah^a | 0.30 | 3.60 | 1.80 |
| Capacity C | ΔC_log.cell/Ah | 1.00 | 5.10 | 2.70 |
| Capacity C | mean SOH_C,log.cell/% | 95.5 | 94.8 | 95.1 |
| Capacity C | SOH_C,log.cell,min/% | 95.2 | 92.8 | 94.2 |
| Capacity C | ΔSOH_C,log.cell/% | 0.8 | 2.7 | 1.4 |
| Capacity C | SOH_E,log.cell,min/% | 87.6 | 85.4 | 86.7 |
| Capacity C | CoV(C_module)/%^a | 0.11 | 0.76 | 0.27 |
| Capacity C | CoV(C_log.cell)/% | 0.15 | 0.41 | 0.19 |
| Capacity C | SOHo_C/% | 99.1 | 97.2 | 98.5 |
| Ohmic resistance R_Ω, module level^b | R̄_Ω,module ± U/mΩ | 8.288 ± 0.018 | 4.003 ± 0.017 | 3.939 ± 0.024 |
| Ohmic resistance R_Ω, module level^b | ΔR_Ω,module/mΩ | 0.066 | 0.076 | 0.035 |
| Ohmic resistance R_Ω, module level^b | CoV(R_Ω,module)/% | 0.30 | 0.85 | 0.25 |
| Ohmic resistance R_Ω, module level^b | CoV(R_Ω,module)/CoV(C_module)^a | 2.7 | 1.1 | 0.9 |
| Ohmic resistance R_Ω, module level^b | SOHo_RΩ,module/% | 99.2 | 98.1 | 99.1 |
| Ohmic resistance R_Ω, logical-cell level | R̄_Ω,log.cell ± U/mΩ | 0.560 ± 0.0043 | 0.404 ± 0.0035 | 0.396 ± 0.0035 |
| Ohmic resistance R_Ω, logical-cell level | ΔR_Ω,log.cell/mΩ | 0.032 | 0.048 | 0.057 |
| Ohmic resistance R_Ω, logical-cell level | CoV(R_Ω,log.cell)/% | 1.45 | 2.32 | 2.39 |
| Ohmic resistance R_Ω, logical-cell level | CoV(R_Ω,log.cell)/CoV(C_log.cell) | 9.7 | 5.7 | 12.6 |
| Ohmic resistance R_Ω, logical-cell level | SOHo_RΩ,log.cell/% | 94.5 | 88.7 | 86.1 |
| Ohmic resistance R_Ω, connector and HVD | ΣR_Ω,conn.+HVD ± U/mΩ | 1.46 ± 0.0004 | 1.73 ± 0.0004 | 1.73 ± 0.0004 |
| DC-pulse resistance R_DC,Δt, logical-cell level | R̄_DC,10s ± U/mΩ | 0.951 ± 0.143 | 0.669 ± 0.276 | 0.693 ± 0.039 |
| DC-pulse resistance R_DC,Δt, logical-cell level | ΔR_DC,10s/mΩ | 0.088 | 0.184 | 0.088 |
| DC-pulse resistance R_DC,Δt, logical-cell level | CoV(R_DC,1s)/% | 2.58 | 4.13 | 2.69 |
| DC-pulse resistance R_DC,Δt, logical-cell level | CoV(R_DC,10s)/% | 2.07 | 3.80 | 2.40 |
| DC-pulse resistance R_DC,Δt, logical-cell level | CoV(R_DC,30s)/% | 1.97 | 3.63 | 2.18 |
| DC-pulse resistance R_DC,Δt, logical-cell level | CoV(R_DC,10s)/CoV(C_log.cell) | 13.8 | 9.3 | 12.6 |
| DC-pulse resistance R_DC,Δt, logical-cell level | SOHo_RDC,10s/% | 91.2 | 76.3 | 88.0 |

<sup>a</sup> *C*<sub>log.cell,min</sub> per module was used to determine Δ*C*<sub>module</sub> and CoV(*C*<sub>module</sub>).<br><sup>b</sup> Comparable module groups only. Pack 1: all modules. Packs 2 and 3: only modules containing 10 logical cells.

A closer field-aged benchmark is provided by Schuster et al. [17], who characterized 1908 individual cells extracted from 2 identical battery electric vehicles (BEVs) after more than 3 years of field operation. For the 2 aged cell populations, the capacity CoVs of 2.25 % and 1.57 % were lower than the corresponding values of 2.56 % and 3.19 % for the EIS-derived ohmic resistance. The polarization resistance exhibited larger CoVs of 8.76 % and 8.78 %. More recently, Hassini et al. [48] reported a capacity CoV of 2.4 % across 36 individual cells disassembled from 3 retired BMW i3 modules, compared with 0.15 % to 0.41 % between logical cells in the present study. Both studies characterized individual cells, whereas the present measurements resolve 2p or 3p logical cells, thereby masking heterogeneity among the parallel-connected cells. Differences in cell chemistry, field history, and measurement method further preclude a direct quantitative comparison. Within these limitations, the results provide field-aged reference magnitudes, and the data from Schuster et al. [17] show the same general ordering observed here, with resistance dispersion exceeding capacity dispersion.

Unlike *R*<sub>Ω</sub>, *R*<sub>DC,Δt</sub> accumulates ohmic, SEI/CEI, charge-transfer, and diffusion contributions, with slower processes building up as Δ*t* increases and therefore providing a time-dependent view of the same resistance heterogeneity [30,49]. Across all packs and all pulse durations, the CoV of the DC-pulse resistance exceeds the corresponding CoV of the ohmic resistance. For a pulse length of 1 s, the CoVs are 2.58 %, 4.13 % and 2.69 % and decrease monotonically to 1.97 %, 3.63 % and 2.18 % at 30 s, matching the trend reported by Rumpf et al. [47]. Nonetheless, the decrease of the CoV with increasing Δ*t* is driven by the growing mean resistance of the logical cells rather than by a narrowing cell-to-cell spread. The mean *R*<sub>DC</sub> rises by approximately 39 % from 1 s to 30 s for all logical cells across all packs as charge-transfer and diffusion overpotentials accumulate, while the standard deviation across logical cells grows by only 6 %, 21 % and 11 % for Packs 1–3, respectively. The decreasing CoV reflects the strong increase in resistance as Δ*t* increases, not a convergence of the cells. In absolute terms, the spread across logical cells also widens at longer pulse durations. At 10 s, SOHo<sub>R,DC,10 s</sub> reaches 91.2 %, 76.3 %, and 88.0 %, so Pack 2 is the most heterogeneous pack by this resistance metric. The cross-pack dispersion ranking is metric-dependent. For *R*<sub>DC</sub>, Pack 2 consistently shows the highest dispersion, followed by Pack 3 and then Pack 1. For *R*<sub>Ω</sub>, Packs 2 and 3 show comparable dispersion, while Pack 1 has the least dispersion.

At the logical-cell level, the *R*<sub>DC</sub> dispersion is not resolved beyond the conservative uncertainty in any of the 3 packs. The reported CoVs and SOHos include measurement-related variability and should be interpreted as upper bounds under this conservative uncertainty perspective. This illustrates the practical trade-off between ohmic and DC-pulse resistance. *R*<sub>Ω</sub> is calculated from five-pulse measurements, allowing for a low-uncertainty evaluation of the early-time ohmic contribution, even when applying a conservative expanded bound. This makes it well-suited for quantitative dispersion analysis in the presence of real heterogeneity. In contrast, DC-pulse resistance requires longer relaxation times and longer measurements at high currents. These conditions lead to larger voltage and SOC variations, greater energy loss, and increased uncertainty. However, *R*<sub>DC</sub> is physically more sensitive to heterogeneity since it captures a wider range of electrochemical processes, including aging-related contributions that evolve over the pulse duration.

Based on our previous work [30], which showed a negative correlation between cell capacity and resistance in 814 lab-aged cells, we expect that cells with the lowest capacities tend to have higher resistance. However, the current logical-cell data only partially support this expectation and do not reveal a consistent trend between logical-cell capacity and *R*<sub>Ω</sub>, as shown in Fig. B.8. Packs 1 and 3 show weak negative PCCs of −0.21 and −0.13, respectively, while Pack 2 shows a moderate positive correlation of *r*(*C*, *R*<sub>Ω</sub>) = 0.44. Sensitivity analyses excluding capacity outliers and identified end-of-module positions do not remove this pack-dependent behavior. Thus, *R*<sub>Ω</sub> and *R*<sub>DC,Δt</sub> do not reliably identify the capacity-limiting logical cells. One plausible explanation is that resistance is determined only at the logical-cell level, whereas capacity-related heterogeneity may originate within individual cells of the parallel group. The increased resistance may not be evident at the logical cell’s terminals, as a lower-resistance branch can carry a larger share of the current. Consequently, the measured resistance of the logical cell reflects the overall equivalent resistance of the parallel network, which can be dominated by the healthier branch, thus masking the increased resistance within the individual cells. At the pack level, Pack 2 combines a lower mean SOH<sub>C</sub> with higher mean ohmic and DC-pulse resistances compared to Pack 3. This cross-pack comparison is qualitatively consistent with the negative capacity–resistance relationship reported for individual cells. However, the limited number of comparable packs and the lack of field histories preclude a definitive pack-level correlation or the attribution of these differences to specific operating conditions.

The module-level CoVs of capacity, ohmic, and DC-pulse resistance are reported in Table C.7. The module with the highest dispersion differs between Packs 2 and 3, so the data do not support the identification of any position-related hotspots. This observation aligns with the module-level SOHo<sub>R</sub> values of 99.2 %, 98.1 % and 99.1 %, indicating that although there is some variation within the modules, the overall heterogeneity remains low.

**Table 6**

Additivity summary for cell-to-pack and module-to-pack resistance scaling. The calculated pack resistance *R*<sub>x,calc</sub> is obtained by summing the respective logical-cell or module resistances along with the connector contributions and is compared with the measured pack resistance *R*<sub>x,meas</sub>.

[Table 6](../assets/table/table-6.csv)

| Pack | Level | Resistance | R_x,calc/mΩ | R_x,meas/mΩ | ΔR_x/mΩ | U_Δ^a/mΩ | ε_Rx/% |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Pack 1 | ΣR_x,log.cell + R_conn. | R_Ω | 51.88 | 51.19 | +0.69 | 0.023 | +1.35 |
| Pack 1 | ΣR_x,log.cell + R_conn. | R_DC,1s | 73.98 | 68.32 | +5.66 | 2.28 | +8.29 |
| Pack 1 | ΣR_x,log.cell + R_conn. | R_DC,10s | 87.01 | 81.98 | +5.02 | 2.11 | +6.13 |
| Pack 1 | ΣR_x,log.cell + R_conn. | R_DC,30s | 102.40 | 95.98 | +6.42 | 2.11 | +6.69 |
| Pack 1 | ΣR_x,mod. + R_conn. | R_Ω | 51.19 | 51.19 | +0.00 | 0.04 | 0.00 |
| Pack 2 | ΣR_x,log.cell + R_conn. | R_Ω | 41.34 | 40.83 | +0.51 | 0.023 | +1.25 |
| Pack 2 | ΣR_x,log.cell + R_conn. | R_DC,1s | 57.37 | 59.03 | −1.66 | 1.61 | −2.80 |
| Pack 2 | ΣR_x,log.cell + R_conn. | R_DC,10s | 67.25 | 68.91 | −1.66 | 1.61 | −2.40 |
| Pack 2 | ΣR_x,log.cell + R_conn. | R_DC,30s | 78.82 | 80.76 | −1.94 | 1.58 | −2.41 |
| Pack 2 | ΣR_x,mod. + R_conn. | R_Ω | 40.88 | 40.83 | +0.05 | 0.04 | +0.13 |
| Pack 3 | ΣR_x,log.cell + R_conn. | R_Ω | 40.57 | 40.00 | +0.57 | 0.020 | +1.42 |
| Pack 3 | ΣR_x,log.cell + R_conn. | R_DC,1s | 59.82 | 55.77 | +4.05 | 1.51 | +7.27 |
| Pack 3 | ΣR_x,log.cell + R_conn. | R_DC,10s | 69.61 | 65.10 | +4.51 | 1.51 | +6.92 |
| Pack 3 | ΣR_x,log.cell + R_conn. | R_DC,30s | 81.61 | 76.66 | +4.95 | 1.59 | +6.46 |
| Pack 3 | ΣR_x,mod. + R_conn. | R_Ω | 40.35 | 40.00 | +0.35 | 0.05 | +0.88 |

<sup>a</sup> Propagated expanded uncertainty of the residual, assuming independent contributions.

Overall, apparent heterogeneity increases from capacity to ohmic resistance to DC-pulse resistance. Under the applied measurement conditions, metrological robustness is higher for *R*<sub>Ω</sub> than for *R*<sub>DC</sub>. At the pack level, Pack 2 combines the lowest mean SOH<sub>C</sub> with the highest mean *R*<sub>Ω</sub> and *R*<sub>DC</sub>, but at the logical-cell level, neither resistance metric reliably identifies the specific logical cells that limit the pack SOH<sub>C</sub>. Capacity, *R*<sub>Ω</sub>, and *R*<sub>DC</sub> therefore remain complementary metrics. Capacity identifies the limiting logical cells, *R*<sub>Ω</sub> resolves dispersion of the ohmic contribution with lower uncertainty, and *R*<sub>DC</sub> adds time-dependent electrochemical and aging sensitivity.

### 4.3. Resistance additivity and component closure

The uncertainty bounds discussed in Section 4.1 provide insight into accuracy when evaluating resistance additivity across 3 scaling paths: cell-to-pack and module-to-pack for ohmic resistance, and cell-to-pack for DC-pulse resistance. For each path, the calculated higher-level resistance is compared with the measured value using the residual definitions from Eq. (7b) and Eq. (7c), together with the propagated expanded uncertainty of the residual *U*<sub>Δ</sub>. Cell contributions dominate the total pack ohmic resistance, accounting for 97.1 % in Pack 1 and 95.7 % to 95.8 % in Packs 2 and 3. Connector and HVD contributions are 1.46 mΩ, 1.73 mΩ and 1.73 mΩ, corresponding to 2.9 % in Pack 1 and 4.2 % to 4.3 % in Packs 2 and 3. Table 6 summarizes the pack-level additivity results for the evaluated scaling paths relative to the measured pack resistance, while the intermediate cell-to-module path for *R*<sub>Ω</sub> is reported in Table D.8.

In the ohmic resistance cell-to-pack path, all residuals are positive and remain small, ranging from 1.25 % to 1.42 %, according to Eq. (7c). All 3 residuals exceed *U*<sub>Δ</sub> by factors of 22 to 30. The consistent positive sign indicates a systematic offset. A plausible explanation for this observation is that the logical-cell measurements include the tab welds and parts of the intercell busbar within the voltage-sensing path. When the logical-cell ohmic resistances are scaled, these additional contributions may accumulate, resulting in the observed pack-level residuals of approximately 5 μΩ to 8 μΩ per logical cell. Although these residuals exceed the propagated uncertainty, their magnitude remains small. Under the applied protocol and instrumentation, the calculated cell-to-pack *R*<sub>Ω</sub> differs from the measured pack resistance by less than 1.5 % for all 3 packs, indicating that cell-to-pack scaling for *R*<sub>Ω</sub> is highly accurate and practically useful.

For the DC-pulse resistance cell-to-pack path, the residuals are larger than for the ohmic resistance in all cases and do not show a consistent sign. Packs 1 and 3 show positive residuals of 6.1 % to 8.3 % and 6.5 % to 7.3 %, whereas Pack 2 shows negative residuals from −2.8 % to −2.4 %. This sign reversal contrasts with the uniformly positive *R*<sub>Ω</sub> residuals. A likely reason is that *R*<sub>DC,Δt</sub> reflects differences between the pack- and logical-cell measurement chains, as well as the stronger state dependence. Nevertheless, it does not indicate a general failure of series additivity.

For the intermediate cell-to-module path of *R*<sub>Ω</sub>, module connector contributions do not enter the comparison. Full results are given in Table D.8. The mean relative residuals are 1.38 %, 1.27 % and 0.56 % for Pack 1 to Pack 3. This predominantly positive bias is consistent with the view that logical-cell ohmic-resistance measurements include a small additional contribution that is already present before the module-to-pack step. The same trend is reflected at the pack level, where cell-to-pack relative residuals are larger than the module-to-pack residuals of less than 0.9 %. Overall, module-to-pack scaling for *R*<sub>Ω</sub> reproduces the measured pack resistance with relative residuals below 0.9 % for all 3 packs.

The close agreement between components and packs makes *R*<sub>Ω</sub> a potential quality-control metric for manufacturing and repair. At each assembly step, the measured resistance could be compared with the sum of the previously characterized components, thereby localizing any excess resistance to newly added connections or hardware once application-specific acceptance limits have been validated. The non-cell contribution of 2.9 % to 4.3 % further shows that changes in pack-level resistance cannot be attributed to cell aging alone, which is relevant to resistance-based battery management system (BMS) state estimation and pack diagnostics [32,33]. For second-life assessment, capacity identifies the limiting logical cell, whereas component-resolved *R*<sub>Ω</sub> helps distinguish logical-cell-related from connector- or HVD-related resistance increases, complementing scalable EIS- and pulse-based capacity-estimation methods [35,36]. The present 3-pack dataset demonstrates the feasibility of this approach, but the general applicability of pass/fail thresholds requires representative BOL reference distributions and validation across a larger pack population.

## 5. Conclusion

This work presents a teardown and component-resolved electrical characterization of 3 field-aged Hyundai Kona Electric battery packs, approximately 5 to 6 years after manufacturing. The assessment resolves logical-cell capacity, the ohmic resistance *R*<sub>Ω</sub>, the DC-pulse resistance *R*<sub>DC,Δt</sub>, and contributions from module connectors and the HVD. Across all 3 packs, capacity dispersion between logical cells remains low, with CoVs of 0.15 %, 0.41 % and 0.19 %. Pack-level capacity was not measured directly. Thus, the minimum logical-cell capacity is used to estimate the pack SOH<sub>C</sub> within the applied test window, yielding estimates of 95.2 %, 92.8 % and 94.2 %. For context, the literature-based energy translation discussed in Section 4.2 yields estimates of 87.6 %, 85.4 %, and 86.7 %. These values remain above the current Euro 7 energy-retention threshold, but this comparison does not constitute a formal compliance assessment.

Although the average aging states are similar across all 3 packs, comparisons between the packs indicate that heterogeneity develops differently across the investigated metrics. Pack 2 exhibits the greatest variation in capacity and has the lowest pack SOH<sub>C</sub> estimate based on the limiting logical cell, whereas Pack 3 exhibits the highest variation in logical-cell ohmic resistance. DC-pulse resistance indicates the highest overall heterogeneity, further highlighting Pack 2 as the most dispersed pack. However, neither resistance metric reliably identifies the specific logical cells that limit the pack’s capacity at the current component levels investigated. Therefore, capacity and resistance should be interpreted as complementary diagnostics rather than interchangeable. Capacity measurements identify the limiting logical cells. Under the applied measurement conditions, ohmic resistance provides the lower-uncertainty quantitative assessment of resistance dispersion, while DC-pulse resistance adds sensitivity to time-dependent electrochemical aging processes.

A simple series network reproduces the measured pack ohmic resistance with cell-to-pack residuals of 1.3 % to 1.5 %. For module-to-pack scaling, the residuals remain below 0.9 % for all 3 packs. In contrast, cell-to-pack DC-pulse resistance scaling yields larger, sign-inconsistent residuals of −2.8 % to 8.3 %. Under the applied protocol and instrumentation, early-time ohmic resistance *R*<sub>Ω</sub> provides a tighter component-to-pack closure than *R*<sub>DC,Δt</sub> and supports the proposed quality-gate concept.

This difference has both a physical and a metrological basis. Evaluation at 400 μs limits contributions from slower charge-transfer and diffusion processes, and the same time-domain measurement principle is applied at each hierarchy level with low uncertainty. In contrast, DC-pulse resistance includes these state-dependent processes and has higher uncertainty in the present measurement chain. This additional sensitivity remains relevant for aging diagnostics but makes component closure more dependent on the measurement conditions. The quantitative advantage of *R*<sub>Ω</sub> is therefore specific to the applied protocol and instrumentation. Furthermore, the contributions from the module connectors and the HVD are not negligible, accounting for 2.9 % of the pack ohmic resistance in Pack 1 and 4.2 % to 4.3 % in Packs 2 and 3.

One key limitation of this work is that the analysis resolves electrical behavior only at the logical-cell level. Capacity-limiting differences within a parallel group remain masked in resistance measurements since the measured logical-cell resistance represents the equivalent response of the parallel network and does not resolve the responses of its individual branches. A cell-level teardown could determine whether resistance-based identification of capacity outliers becomes feasible once this heterogeneity is resolved directly. The reported capacity-based pack estimates are derived from the minimum logical-cell capacity measured separately over the voltage range of 2.5 V to 4.2 V. Thus, they do not directly represent vehicle-usable capacity or energy, which may differ because of pack-level voltage limits, balancing, thermal conditions, and control strategies. The study is further limited to 3 packs from a single vehicle model and cell type. Its quantitative results characterize the systems investigated and should not be interpreted as population-wide estimates for field-aged EV battery packs. Larger teardown datasets, obtained using consistent procedures and definitions, are required to compare dispersion and aging patterns across battery systems. In this context, a thorough uncertainty assessment is crucial, as it not only influences measurement accuracy and precision but also determines whether observed differences and variations are physically meaningful.

## CRediT authorship contribution statement

**Marco Fischer:** Writing – original draft, Visualization, Validation, Software, Resources, Methodology, Investigation, Formal analysis, Data curation, Conceptualization. **Martin J. Brand:** Writing – review & editing, Resources, Data curation, Conceptualization. **Alexander Schröder:** Data curation. **Andreas Jossen:** Writing – review & editing, Supervision, Project administration, Funding acquisition.

## Declaration of generative AI and AI-assisted technologies in the manuscript preparation process

During the preparation and revision of this work, the authors used Grammarly and ChatGPT to support language editing and improve the readability. The authors reviewed and edited the output as needed and take full responsibility for the content of the published article.

## Declaration of competing interest

The authors declare the following financial interests/personal relationships which may be considered as potential competing interests: Marco Fischer reports equipment, drugs, or supplies was provided by Li.plus GmbH. If there are other authors, they declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

## Acknowledgments

This research was financially supported by the German Federal Ministry for Economic Affairs and Energy (BMWE) in the project accuRate (03ETE032C). The responsibility for this publication rests with the authors.

## Appendix A. Evaluation-time sensitivity of the early-time ohmic resistance

See Fig. A.7.

[Fig. A.7](../assets/figure/figure-a-7.jpg)

**Fig. A.7.** Evaluation-time sensitivity of the early-time ohmic resistance *R*<sub>Ω</sub> across component levels. Relative deviations are calculated with respect to the selected evaluation time of 400 μs. (a) Resistance evaluated at 200 μs relative to *R*<sub>400 μs</sub>. (b) Resistance evaluated at 450 μs relative to *R*<sub>400 μs</sub>. Boxplots represent the distributions across logical cells and modules of the respective pack, with black squares indicating the arithmetic mean and points outside the whiskers identified according to the 1.5 × IQR criterion. At the pack level, one value is shown for each physical pack.

## Appendix B. Correlation between early-time ohmic resistance and logical-cell capacity

See Fig. B.8.

[Fig. B.8](../assets/figure/figure-b-8.jpg)

**Fig. B.8.** Relationship between logical-cell capacity *C* and ohmic resistance *R*<sub>Ω</sub> and sensitivity of the corresponding correlation. (a)–(c) show the logical-cell measurements for Packs 1–3, respectively, together with the linear fit and the PCC *r*(*C*, *R*<sub>Ω</sub>). Capacity outliers are identified using the 1.5 × IQR criterion, while end-of-module positions are highlighted for Packs 2 and 3 due to the identified connection-geometry effect. (d) shows the sensitivity of the PCC to the exclusion of capacity outliers and end-of-module positions. Horizontal intervals denote the 95 % confidence intervals of *r* based on the Fisher *z* transformation. Sensitivity scenarios are shown only where applicable.

## Appendix C. Module-level ohmic resistance dispersion

See Table C.7.

**Table C.7**

Module-level CoVs for capacity and resistance metrics across 3 field-aged packs.

[Table C.7](../assets/table/table-c-7.csv)

| Pack | Module | n_logical cells | CoV(C_CCCV)/% | CoV(R_Ω)/% | CoV(R_DC,1s)/% | CoV(R_DC,10s)/% | CoV(R_DC,30s)/% |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Pack 1 | Module 1 | 15 | 0.14 | 1.14 | 1.38 | 0.96 | 1.00 |
| Pack 1 | Module 2 | 15 | 0.14 | 1.70 | 1.06 | 0.98 | 1.10 |
| Pack 1 | Module 3 | 15 | 0.15 | 1.54 | 1.12 | 0.79 | 0.84 |
| Pack 1 | Module 4 | 15 | 0.18 | 1.28 | 1.83 | 1.55 | 1.56 |
| Pack 1 | Module 5 | 15 | 0.12 | 1.14 | 2.82 | 2.37 | 2.13 |
| Pack 1 | Module 6 | 15 | 0.15 | 1.84 | 2.41 | 1.68 | 1.74 |
| Pack 2 | Module 1 | 10 | 0.58 | 2.32 | 2.62 | 2.37 | 2.18 |
| Pack 2 | Module 2 | 10 | 0.46 | 1.85 | 4.35 | 4.13 | 4.16 |
| Pack 2 | Module 3 | 10 | 0.26 | 2.37 | 1.67 | 1.44 | 1.49 |
| Pack 2 | Module 4 | 9 | 0.45 | 3.23 | 5.71 | 4.88 | 4.37 |
| Pack 2 | Module 5 | 10 | 0.19 | 1.59 | 1.60 | 1.43 | 1.55 |
| Pack 2 | Module 6 | 9 | 0.13 | 2.17 | 4.25 | 3.58 | 3.17 |
| Pack 2 | Module 7 | 10 | 0.11 | 1.95 | 1.92 | 1.80 | 1.75 |
| Pack 2 | Module 8 | 10 | 0.25 | 3.19 | 2.64 | 2.37 | 2.24 |
| Pack 2 | Module 9 | 10 | 0.12 | 1.65 | 3.70 | 3.23 | 3.04 |
| Pack 2 | Module 10 | 10 | 0.67 | 1.75 | 2.07 | 2.11 | 1.92 |
| Pack 3 | Module 1 | 10 | 0.23 | 2.01 | 2.29 | 1.93 | 1.60 |
| Pack 3 | Module 2 | 10 | 0.14 | 2.68 | 2.92 | 2.78 | 2.14 |
| Pack 3 | Module 3 | 10 | 0.12 | 2.07 | 2.06 | 1.82 | 1.52 |
| Pack 3 | Module 4 | 9 | 0.09 | 2.71 | 1.70 | 1.76 | 1.39 |
| Pack 3 | Module 5 | 10 | 0.11 | 1.89 | 1.47 | 1.39 | 1.23 |
| Pack 3 | Module 6 | 9 | 0.21 | 4.16 | 2.25 | 1.74 | 1.72 |
| Pack 3 | Module 7 | 10 | 0.13 | 2.07 | 2.60 | 2.16 | 1.83 |
| Pack 3 | Module 8 | 10 | 0.18 | 2.29 | 2.09 | 1.77 | 1.69 |
| Pack 3 | Module 9 | 10 | 0.34 | 2.12 | 2.13 | 1.73 | 1.66 |
| Pack 3 | Module 10 | 10 | 0.15 | 2.54 | 2.18 | 1.71 | 1.63 |

## Appendix D. Cell-to-module ohmic resistance additivity

See Table D.8.

**Table D.8**

Additivity summary for cell-to-module scaling. The calculated module resistance *R*<sub>x,calc</sub> is obtained by summing the respective ohmic resistances of the logical cells and is compared with the measured module resistance *R*<sub>x,meas</sub>.

[Table D.8](../assets/table/table-d-8.csv)

| Pack | Module | R_Ω,meas/mΩ | ΣR_Ω,log.cell/mΩ | ΔR_Ω/mΩ | U_Δ^a/mΩ | ε_RΩ/% |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | 1 | 8.33 | 8.44 | +0.11 | 0.02 | +1.35 |
| 1 | 2 | 8.29 | 8.40 | +0.11 | 0.01 | +1.34 |
| 1 | 3 | 8.30 | 8.41 | +0.12 | 0.01 | +1.42 |
| 1 | 4 | 8.25 | 8.40 | +0.15 | 0.02 | +1.78 |
| 1 | 5 | 8.29 | 8.41 | +0.12 | 0.01 | +1.43 |
| 1 | 6 | 8.28 | 8.36 | +0.08 | 0.02 | +0.98 |
| 2 | 1 | 3.95 | 4.02 | +0.06 | 0.01 | +1.62 |
| 2 | 2 | 4.02 | 4.08 | +0.05 | 0.01 | +1.31 |
| 2 | 3 | 4.04 | 4.10 | +0.06 | 0.01 | +1.50 |
| 2 | 4^b | 3.56 | 3.61 | +0.06 | 0.01 | +1.58 |
| 2 | 5 | 4.02 | 4.08 | +0.06 | 0.01 | +1.37 |
| 2 | 6^b | 3.56 | 3.62 | +0.06 | 0.02 | +1.75 |
| 2 | 7 | 3.97 | 4.00 | +0.04 | 0.02 | +0.92 |
| 2 | 8 | 4.03 | 4.08 | +0.05 | 0.02 | +1.11 |
| 2 | 9 | 3.96 | 4.00 | +0.04 | 0.01 | +1.07 |
| 2 | 10 | 4.01 | 4.03 | +0.02 | 0.01 | +0.44 |
| 3 | 1 | 3.92 | 3.96 | +0.04 | 0.01 | +1.08 |
| 3 | 2 | 3.93 | 3.97 | +0.04 | 0.01 | +0.93 |
| 3 | 3 | 3.93 | 3.97 | +0.04 | 0.01 | +0.94 |
| 3 | 4^b | 3.55 | 3.56 | +0.01 | 0.01 | +0.16 |
| 3 | 5 | 3.96 | 3.97 | +0.01 | 0.02 | +0.27 |
| 3 | 6^b | 3.54 | 3.56 | +0.02 | 0.01 | +0.42 |
| 3 | 7 | 3.92 | 3.97 | +0.05 | 0.01 | +1.20 |
| 3 | 8 | 3.97 | 3.96 | −0.01 | 0.02 | −0.29 |
| 3 | 9 | 3.96 | 3.98 | +0.02 | 0.01 | +0.46 |
| 3 | 10 | 3.94 | 3.96 | +0.02 | 0.02 | +0.46 |

<sup>a</sup> Propagated expanded uncertainty of the residual, combining repeatability uncertainties at the logical-cell and module levels with Student-*t*-based coverage factors and assuming independent contributions.<br><sup>b</sup> The indicated module contains 9 logical cells.

## Data availability

Data will be made available on request.

## References

- [1] Wassiliadis N, Steinsträter M, Schreiber M, Rosner P, Nicoletti L, Schmid F, Ank M, Teichert O, Wildfeuer L, Schneider J, Koch A, König A, Glatz A, Gandlgruber J, Kröger T, Lin X, Lienkamp M. Quantifying the state of the art of electric powertrains in battery electric vehicles: Range, efficiency, and lifetime from component to system level of the Volkswagen ID.3. ETransportation 2022;12:100167. http://dx.doi.org/10.1016/j.etran.2022.100167.

- [2] Zubi G, Dufo-López R, Carvalho M, Pasaoglu G. The lithium-ion battery: State of the art and future perspectives. Renew Sustain Energy Rev 2018;89:292–308. http://dx.doi.org/10.1016/j.rser.2018.03.002.

- [3] Rüther T, Hileman W, Trimboli MS, Plett GL, Dubarry M, Kumar N, Marco J, Roehrer F, Jossen A, Schöberl J, Lienkamp M, Bohlen O, Danzer MA. Battery pack states, properties, and characterization techniques beyond cell level. Cell Rep Phys Sci 2025;6(11):102919. http://dx.doi.org/10.1016/j.xcrp.2025.102919.

- [4] Celik S, Ma Z, Hong Z, Blömeke A, Wasylowski D, Sauer DU. Electrochemical impedance spectroscopy–based diagnosis of cell imbalances in series–connected battery modules. Batter Supercaps 2025;8(12):e202500284. http://dx.doi.org/10.1002/batt.202500284, URL https://chemistry-europe.onlinelibrary.wiley.com/doi/10.1002/batt.202500284.

- [5] Ank M, Göhmann J, Lienkamp M. Multi-cell testing topologies for defect detection using electrochemical impedance spectroscopy: A combinatorial experiment-based analysis. Batteries 2023;9(8):415. http://dx.doi.org/10.3390/batteries9080415, URL https://www.mdpi.com/2313-0105/9/8/415.

- [6] Togasaki N, Yokoshima T, Oguma Y, Osaka T. Detection of unbalanced voltage cells in series-connected lithium-ion batteries using single-frequency electrochemical impedance spectroscopy. J Electrochem Sci Technol 2021;12(4):415–23. http://dx.doi.org/10.33961/jecst.2021.00115, URL https://www.jecst.org/journal/view.php?number=402.

- [7] Naguib M, Kollmeyer P, Emadi A. Lithium-ion battery pack robust state of charge estimation, cell inconsistency, and balancing: Review. IEEE Access 2021;9:50570–82. http://dx.doi.org/10.1109/ACCESS.2021.3068776.

- [8] Wildfeuer L, Wassiliadis N, Reiter C, Baumann M, Lienkamp M. Experimental characterization of Li-Ion battery resistance at the cell, module and pack level. In: 2019 fourteenth international conference on ecological vehicles and renewable energies. IEEE; 2019, p. 1–12. http://dx.doi.org/10.1109/EVER.2019.8813578.

- [9] Kampker A, Wessel S, Fiedler F, Maltoni F. Battery pack remanufacturing process up to cell level with sorting and repurposing of battery cells. J Remanufacturing 2021;11(1):1–23. http://dx.doi.org/10.1007/s13243-020-00088-6, URL https://link.springer.com/article/10.1007/s13243-020-00088-6.

- [10] Offer GJ, Yufit V, Howey DA, Wu B, Brandon NP. Module design and fault diagnosis in electric vehicle batteries. J Power Sources 2012;206:383–92. http://dx.doi.org/10.1016/j.jpowsour.2012.01.087.

- [11] Schindler M, Jocher P, Durdel A, Jossen A. Analyzing the aging behavior of lithium-ion cells connected in parallel considering varying charging profiles and initial cell-to-cell variations. J Electrochem Soc 2021;168(9):090524. http://dx.doi.org/10.1149/1945-7111/ac2089.

- [12] Wang X, Fang Q, Dai H, Chen Q, Wei X. Investigation on cell performance and inconsistency evolution of series and parallel lithium–Ion battery modules. Energy Technol 2021;9(7):2100072. http://dx.doi.org/10.1002/ente.202100072, URL https://onlinelibrary.wiley.com/doi/10.1002/ente.202100072.

- [13] Al-Amin M, Barai A, Ashwin TR, Marco J. An insight to the degradation behaviour of the parallel connected lithium-ion battery cells. Energies 2021;14(16):4716. http://dx.doi.org/10.3390/en14164716, URL https://www.mdpi.com/1996-1073/14/16/4716.

- [14] Baumann M, Wildfeuer L, Rohr S, Lienkamp M. Parameter variations within Li-Ion battery packs – theoretical investigations and experimental quantification. J Energy Storage 2018;18:295–307. http://dx.doi.org/10.1016/j.est.2018.04.031.

- [15] Baumhöfer T, Brühl M, Rothgang S, Sauer DU. Production caused variation in capacity aging trend and correlation to initial cell performance. J Power Sources 2014;247:332–8. http://dx.doi.org/10.1016/j.jpowsour.2013.08.108, URL https://www.sciencedirect.com/science/article/pii/S0378775313014584.

- [16] Pastor-Fernández C, Bruen T, Widanage WD, Gama-Valdez MA, Marco J. A study of cell-to-cell interactions and degradation in parallel strings: Implications for the battery management system. J Power Sources 2016;329:574–85. http://dx.doi.org/10.1016/j.jpowsour.2016.07.121.

- [17] Schuster SF, Brand MJ, Berg P, Gleissenberger M, Jossen A. Lithium-ion cell-to-cell variation during battery electric vehicle operation. J Power Sources 2015;297:242–51. http://dx.doi.org/10.1016/j.jpowsour.2015.08.001, URL https://www.sciencedirect.com/science/article/pii/S0378775315301555.

- [18] Gogoana R, Pinson MB, Bazant MZ, Sarma SE. Internal resistance matching for parallel-connected lithium-ion cells and impacts on battery pack cycle life. J Power Sources 2014;252:8–13. http://dx.doi.org/10.1016/j.jpowsour.2013.11.101, URL https://www.sciencedirect.com/science/article/pii/S0378775313019447.

- [19] Song Z, Yang X-G, Yang N, Delgado FP, Hofmann H, Sun J. A study of cell-to-cell variation of capacity in parallel-connected lithium-ion battery cells. ETransportation 2021;7:100091. http://dx.doi.org/10.1016/j.etran.2020.100091.

- [20] International Organization for Standardization. ISO 12405-4:2018, Electrically propelled road vehicles — Test specification for lithium-ion traction battery packs and systems: Part 4: Performance testing. 2018, URL https://www.iso.org/standard/71407.html.

- [21] Deutsches Institut für Normung eV. DIN EN IEC 62660-1 (VDE 0510-33):2020-07, Lithium-Ionen-Sekundärzellen für den Antrieb von Elektrostraßenfahrzeugen: Teil 1: Prüfung des Leistungsverhaltens (IEC 62660-1:2018); Deutsche Fassung EN IEC 62660-1:2019. 2020-07, URL https://www.dinmedia.de/en/standard/din-en-iec-62660-1/321514971.

- [22] Christophersen JP. Battery test manual for electric vehicles. Idaho Falls, Idaho, USA: Idaho National Laboratory; 2015, http://dx.doi.org/10.2172/1186745, INL/EXT-15-34184. URL https://www.osti.gov/biblio/1186745.

- [23] State Administration for Market Regulation and Standardization Administration of the People’s Republic of China. GB/T 31486-2024, Electrical performance requirements and test methods for traction battery of electric vehicle. 2024-09-29, URL https://openstd.samr.gov.cn/bzgk/std/newGbInfo?hcno=B6CF5BFB2A04A9E9890A271BAA6F153C.

- [24] Stroe D-I, Swierczynski M, Stroe A-I, Knudsen Kær S. Generalized characterization methodology for performance modelling of lithium-ion batteries. Batteries 2016;2(4):37. http://dx.doi.org/10.3390/batteries2040037.

- [25] Pastor-Fernández C, Yu TF, Widanage WD, Marco J. Critical review of non-invasive diagnosis techniques for quantification of degradation modes in lithium-ion batteries. Renew Sustain Energy Rev 2019;109:138–59. http://dx.doi.org/10.1016/j.rser.2019.03.060, URL https://www.sciencedirect.com/science/article/pii/S136403211930200X.

- [26] Gomez MR, Natterer J, Fischer M, Thielmann J, Zonta E, Jossen A. Statistical analysis for robust battery state estimation: Demonstrating ANOVA-driven feature selection with electrochemical impedance spectroscopy. J Power Sources 2026;672:239526. http://dx.doi.org/10.1016/j.jpowsour.2026.239526, URL https://www.sciencedirect.com/science/article/pii/S0378775326002764.

- [27] Ludwig S, Zilberman I, Oberbauer A, Rogge M, Fischer M, Rehm M, Jossen A. Adaptive method for sensorless temperature estimation over the lifetime of lithium-ion batteries. J Power Sources 2022;521:230864. http://dx.doi.org/10.1016/j.jpowsour.2021.230864.

- [28] Natterer J, Gomez MR, Zonta E, Thielmann J, Rehm M, Cronau M, Jossen A. Can aging effects in Li-ion cells be quantified with electrochemical impedance spectroscopy under varying state of charge and temperature? applying inferential statistics. J Power Sources 2026;676:239896. http://dx.doi.org/10.1016/j.jpowsour.2026.239896.

- [29] Wildfeuer L, Gieler P, Karger A. Combining the distribution of relaxation times from EIS and time-domain data for parameterizing equivalent circuit models of lithium-ion batteries. Batteries 2021;7(3):52. http://dx.doi.org/10.3390/batteries7030052.

- [30] Fischer M, Brand MJ, Karger A, Gomez MR, Rehm M, Natterer J, Jossen A. How degradation of lithium-ion batteries impacts capacity fade and resistance increase: A systematic, correlative analysis. J Power Sources 2025;656:237921. http://dx.doi.org/10.1016/j.jpowsour.2025.237921.

- [31] Bilfinger P, Rosner P, Schreiber M, Kröger T, Gamra KA, Ank M, Wassiliadis N, Dietermann B, Lienkamp M. Battery pack diagnostics for electric vehicles: Transfer of differential voltage and incremental capacity analysis from cell to vehicle level. ETransportation 2024;22:100356. http://dx.doi.org/10.1016/j.etran.2024.100356.

- [32] Bilfinger P, Rosner P, Schreiber M, Brehler T, Grosu C, Schöberl J, Abo Gamra K, Lienkamp M. Battery pack diagnostics for electric vehicles: Robustness of the state of health measurement and differential voltage analysis at the vehicle level. ETransportation 2026;28:100589. http://dx.doi.org/10.1016/j.etran.2026.100589.

- [33] Wang Z, Shi D, Zhao J, Chu Z, Guo D, Eze C, Qu X, Lian Y, Burke AF. Battery health diagnostics: Bridging the gap between academia and industry. ETransportation 2024;19:100309. http://dx.doi.org/10.1016/j.etran.2023.100309.

- [34] Braco E, San Martin I, Berrueta A, Sanchis P, Ursua A. Experimental assessment of first- and second-life electric vehicle batteries: Performance, capacity dispersion, and aging. IEEE Trans Ind Appl 2021;57(4):4107–17. http://dx.doi.org/10.1109/TIA.2021.3075180.

- [35] Fan W, Jiang B, Wang X, Yuan Y, Zhu J, Wei X, Dai H. Enhancing capacity estimation of retired electric vehicle lithium-ion batteries through transfer learning from electrochemical impedance spectroscopy. ETransportation 2024;22:100362. http://dx.doi.org/10.1016/j.etran.2024.100362.

- [36] Zhang J, Tong Z, Ren N, Chen X, Cao XE. Developing an efficient hierarchical regrouping method for uncharacterized retired electric vehicle Li-ion batteries based on partial pulse discharge curves. ETransportation 2026;28:100591. http://dx.doi.org/10.1016/j.etran.2026.100591.

- [37] Waag W, Käbitz S, Sauer DU. Experimental investigation of the lithium-ion battery impedance characteristic at various conditions and aging states and its influence on the application. Appl Energy 2013;102:885–97. http://dx.doi.org/10.1016/j.apenergy.2012.09.030.

- [38] Barai A, Uddin K, Widanage WD, McGordon A, Jennings P. A study of the influence of measurement timescale on internal resistance characterisation methodologies for lithium-ion cells. Sci Rep 2018;8(1):21. http://dx.doi.org/10.1038/s41598-017-18424-5.

- [39] Huber C, Horsche M, Brand M, Schmidt K. Method, apparatus and computer program for determining an impedance of an electrically conducting device: European patent EP 3 438 682 B1. 2023, URL https://data.epo.org/publication-server/rest/v1.2/patents/EP3438682NWB1/document.pdf.

- [40] European Parliament and Council of the European Union. Regulation (EU) 2024/1257 of the European Parliament and of the Council of 24 April 2024 on type-approval of motor vehicles and engines and of systems, components and separate technical units intended for such vehicles, with respect to their emissions and battery durability (Euro 7), amending Regulation (EU) 2018/858 of the European Parliament and of the Council and repealing Regulations (EC) No 715/2007 and (EC) No 595/2009 of the European Parliament and of the Council, Commission Regulation (EU) No 582/2011, Commission Regulation (EU) 2017/1151, Commission Regulation (EU) 2017/2400 and Commission Implementing Regulation (EU) 2022/1362. 2024, URL http://data.europa.eu/eli/reg/2024/1257/oj.

- [41] Kindermann FM, Noel A, Erhard SV, Jossen A. Long-term equalization effects in Li-ion batteries due to local state of charge inhomogeneities and their impact on impedance measurements. Electrochim Acta 2015;185:107–16. http://dx.doi.org/10.1016/j.electacta.2015.10.108.

- [42] Landinger TF, Schwarzberger G, Jossen A. A physical-based high-frequency model of cylindrical lithium-ion batteries for time domain simulation. IEEE Trans Electromagn Compat 2020;62(4):1524–33. http://dx.doi.org/10.1109/TEMC.2020.2996414.

- [43] Joint Committee for Guides in Metrology. JCGM 100:2008, Evaluation of measurement data: Guide to the expression of uncertainty in measurement. (100). 2008, http://dx.doi.org/10.59161/JCGM100-2008E, URL https://www.bipm.org/en/doi/10.59161/jcgm100-2008e.

- [44] Preger Y, Wittman R, Harris SJ, Dubarry M. Are capacity and energy loss equivalent metrics for battery aging reporting? J Electrochem Energy Convers Storage 2026;23(2):021109. http://dx.doi.org/10.1115/1.4071224.

- [45] Wildfeuer L, Lienkamp M. Quantifiability of inherent cell-to-cell variations of commercial lithium-ion batteries. ETransportation 2021;9:100129. http://dx.doi.org/10.1016/j.etran.2021.100129.

- [46] Schindler M, Sturm J, Ludwig S, Durdel A, Jossen A. Comprehensive analysis of the aging behavior of nickel-rich, silicon-graphite lithium-ion cells subject to varying temperature and charging profiles. J Electrochem Soc 2021;168(6):060522. http://dx.doi.org/10.1149/1945-7111/ac03f6, URL https://iopscience.iop.org/article/10.1149/1945-7111/ac03f6.

- [47] Rumpf K, Naumann M, Jossen A. Experimental investigation of parametric cell-to-cell variation and correlation based on 1100 commercial lithium-ion cells. J Energy Storage 2017;14:224–43. http://dx.doi.org/10.1016/j.est.2017.09.010, URL https://www.sciencedirect.com/science/article/pii/S2352152X17302633.

- [48] Hassini M, Mintsa-Eya C, Redondo-Iglesias E, Venet P. Influence of cell position on the capacity of retired batteries: Experimental and statistical studies. In: IECON 2025 – 51st annual conference of the IEEE industrial electronics society. IEEE; 2025, p. 1–5. http://dx.doi.org/10.1109/IECON58223.2025.11221867.

- [49] Edge JS, O’Kane S, Prosser R, Kirkaldy ND, Patel AN, Hales A, Ghosh A, Ai W, Chen J, Yang J, Li S, Pang M-C, Bravo Diaz L, Tomaszewska A, Marzook MW, Radhakrishnan KN, Wang H, Patel Y, Wu B, Offer GJ. Lithium ion battery degradation: what you need to know. Phys Chem Chem Phys : PCCP 2021;23(14):8200–21. http://dx.doi.org/10.1039/d1cp00359c.

## Conversion notes

- Source: M. Fischer, M.J. Brand, A. Schröder, A. Jossen, eTransportation 30 (2026) 100636, https://doi.org/10.1016/j.etran.2026.100636 (published version of record, available online 18 September 2026).
- License: open access under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Reuse requires attribution to the original article.
- Data availability as stated in the article: data will be made available on request. No raw data or code is included in this package.
