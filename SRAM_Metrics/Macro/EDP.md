# EDP (Energy Delay Product)

## 定义与适用范围

**能量延时积**（Energy-Delay Product，EDP）是一次有效的静态随机存取存储器（Static Random Access Memory，SRAM）宏访问的供电能量和访问延时的乘积。按读、写分别报告：

$$
\mathrm{EDP}_{\mathrm{op},i}=E_{\mathrm{op},i}\,D_{\mathrm{op},i},
\qquad \mathrm{op}\in\{\mathrm{R},\mathrm{W}\}.
$$

$E_{\mathrm{op},i}$（J）和 $D_{\mathrm{op},i}$（s）分别为第 $i$ 次同一访问的能量和延时。每次访问的 EDP 以 J·s 表示，$1\,\mathrm{pJ}\cdot\mathrm{ns}=10^{-21}\,\mathrm{J}\cdot\mathrm{s}$。Gonzalez 和 Horowitz 以此乘积评估固定工作量的处理器能效与性能；宏级口径将固定工作量定义为一次有明确位宽的读或写访问。[1, pp. 1277–1279]

| 指标 | 定义与用途 |
| --- | --- |
| EDP | $E D$，比较同口径访问的能量与延时。默认使用完整访问窗内的总供电能量；扣除同条件待机基线的增量 EDP 单列。 |
| 功率延时积（Power-Delay Product，PDP） | $\overline P D$，单位 W·s = J。当功率正好在时长 $D$ 的同一窗内取平均时，PDP 等于该窗能量；覆盖恢复的整次访问能量仍按实际访问窗积分。 |
| 能量延时面积积（Energy-Delay-Area Product，[EDAP](EDAP.md)） | $E D A_{\mathrm{macro}}$，另计完整宏的放置面积；面积相同且 $E,D$ 口径一致时，两者排序相同。 |

在同一电源边界、同一时窗 $T$ 和同一操作序列内，测得平均功率 $\overline P$（W）并计数 $N>0$，按实际访问率 $r=N/T$（次/s）计算平均能量 $\overline E=\overline P/r$（J/次）。分子和分母须对应同一读写比例、并发、空闲及失败处理规则；纯读或纯写用隔离序列或经验证的能量分摊。窗口覆盖整时钟周期时，只有所计访问数等于周期数，$r$ 才等于时钟频率。若 $D$ 固定且与该序列匹配，可用 $\overline E D$；含空闲或共用活动时须标为批次摊销结果。$D$ 变化时，批次平均功率无法恢复逐次 $E_iD_i$。[2, Power/Delay Characterization] [7, Sec. IV] [8, Sec. V, Figs. 19–20] [9, Sec. V-C]

## 物理机制与变异

**电压与访问恢复**：降低供电通常降低电容切换能量，驱动电流也会减小，延长字线（Wordline，WL）传播、位线（Bitline，BL）发展、写入或恢复时间。总访问能量还计入窗内待机电流及辅助电路；窗变长时，静态能量可能抵消切换能量下降。Sinangil 等的 65 nm 宏实测分别报告能量和访问频率：约 0.4 V 时总能量低于 11 pJ/次（128 bit）；继续降压时，较长的时钟周期增大每次访问分摊的漏电能量。该频率曲线用于吞吐评估。[7, Sec. IV, Fig. 18] [8, Sec. V, Figs. 19–20] [9, Sec. V, Figs. 21–22]

**组织、数据与工艺条件**：分存储体（Bank）、子阵列尺寸、全局树缓冲及引脚位置会重分配局部与全局延时及充放电能量；写辅助可缩短翻转时间，也会消耗驱动能量。地址、翻转方向、掩码、供电压降、输出负载以及工艺、电压和温度（Process, Voltage and Temperature，PVT）同时影响 $E,D$ 及失败率。须按同一宏版次、样片或失配样本、PVT 和事务保留配对。Liu 等在典型角、27 °C 的互补场效应晶体管（Complementary Field-Effect Transistor，CFET）子阵列仿真中，用同一写工作点提取写能量和写延时；采用简化外部写辅助供电，能量未计专用写外围。[5, Secs. V–VI] [6, Secs. 6.2, 7.1–7.5] [12, Secs. III-B, III-E, Fig. 15] [13, Sec. IV, Figs. 16–19] [14, Sec. III, Figs. 6–10]

## 宏边界与提取口径

| 对象 | 计量或观察边界 |
| --- | --- |
| **能量** | 在宏供电边界端口量相对同一参考点的电位和流入宏的电流，按实际参考端与回流拓扑计量。纳入宏内子阵列、局部／全局互连、译码、数据通路、内部时钟／控制及辅助；外供辅助、独立 I/O 和偏置轨按实际供电边界记录，同一辅助电路只计一次。板级稳压器、激励源、测试外围和独立供电的片外负载须声明是否计入；无法去嵌时，按实际边界报告。 |
| **读延时** | 从宏接受读请求的规定时钟沿或握手事件，至规范负载下宏 DOUT 的目标位全部达到有效门槛并保持。记录起止阈值和极性；仿真须验证数据正确，硅测须校准触发、输出及通道偏差。 |
| **写延时** | 从宏接受写请求到接口定义的写完成；仅当协议规定提交时才用写确认作终点。若接口无直接完成观测，可用宏接受至所有应翻转位的已验证内部稳定事件，标为内部写延时；通过读回检查掩码和受扰位。同值写保留能量；无有效完成事件时不计入延时或 EDP 样本。 |
| **周期与代理量** | 最小时钟周期、持续访问率、写后最早合法读间隔和访问延时分别报告。前两者反映可重复接受访问的能力；流水线延时可跨数周期。写后读功能扫描须核对读通路及转发规则；最早合法读给出接口就绪代理，满足无旁路且已校准验证条件时可给写完成上界。 |
| **操作与位数** | 报告可用容量、端口、接受命令数、成功事务数、位宽、掩码、有效交付位数、实际翻转及失败／重试。每访问 EDP 以整次事务能量计算；若按有效位数 $b>0$ 归一，单列 $(E/b)D$、原始 $E$ 和 $b$，保持读／写交付位定义一致。 |

[2, Power/Delay Characterization] [3, Figs. 15.2.6–7] [4, Secs. 3–5] [6, Secs. 2.3.2, 2.4.2] [10, Sec. III, Figs. 16–17] [11, Sec. 4.4] [15, Secs. II–III]

## 测量与提取方法

### 【前置条件】

锁定宏标识与版次，使用寄生参数提取（Parasitic Extraction，PEX）网表或硅样片。记录电源边界与参考端、PVT、样片或失配种子、地址和初态、负载及输入门槛、读写比例、翻转方向、掩码、测试频率、空闲及并发。固定有效延时、恢复及功能通过规则。按 [读能量 RE](../Subarray/Read_Energy.md#测量与提取方法)、[写能量 WE](../Subarray/Write_Energy.md#测量与提取方法)、[读延时 RD](../Subarray/Read_Delay.md#测量与提取方法) 和 [写延时 WD](../Subarray/Write_Delay.md#测量与提取方法) 核对测试电路、探针和判据；将局部激励接到实际宏控制通路，纳入全局访问树、宏内辅助和实际输出接口。[2, Power/Delay Characterization] [6, Secs. 2.3.2, 2.4.2] [11, Secs. 3, 4.4]

### 【步骤／方法】

1. **预置并激励**：在积分窗之外初始化和校验数据，恢复到规定的就绪状态。先做隔离读／写，覆盖近／远端、数据方向及目标掩码；再按规定运行重复或混合工作负载。保存操作标识、请求接受、读结果／写完成、预充、辅助释放、恢复和验证标记。
2. **采集宏供电和接口事件**：后仿真保存同次访问的各轨电压、电流和接口波形；硅测在同一样片、偏置、温度、端口活动及负载下同步触发供电和接口采样，校准零点、增益、压降、带宽、时差和去耦补充电荷。用 [RE](../Subarray/Read_Energy.md) 的入端功率积分和 [WD](../Subarray/Write_Delay.md) 的稳定及读回方法核对符号、窗口和写终点。仅能采到整批平均功率时，按同一窗口内的实际访问计数换算，声明统计口径和访问成功率。
3. **提取同次 $E,D$**：隔离测量取从访问前就绪到该次结果有效、预充及电源轨／去耦均恢复到规定状态的窗 $[t_0,t_1]$，保证 $t_1\ge t_{\mathrm{valid}}$，覆盖该次访问的驱动、输出活动和恢复；端口电流流入宏为正，回送能量保留符号。按协议或已校准内部判据提取 $D=t_{\mathrm{valid}}-t_{\mathrm{accept}}$。在同样供电、温度、时钟和等时窗的待机对照下可另算增量量。保存每轨积分、窗端和恢复状态：

   $$
   E_{\mathrm{tot}}=\int_{t_0}^{t_1}\sum_k [V_k(t)-V_{\mathrm{ref}}(t)] I_{k,\mathrm{in}}(t)\,\mathrm{d}t,
   \qquad E_{\mathrm{inc}}=E_{\mathrm{tot}}-E_{\mathrm{idle}}.
   $$

   $k$ 为纳入边界的计量端（按实际接法含回流），$V_k,V_{\mathrm{ref}}$ 用同一电位参考（V），$I_{k,\mathrm{in}}$ 为端口流入电流（A），$E_{\mathrm{idle}}$ 为等时长待机基线能量（J）。

**注意事项**：共用电源轨的流水或并发访问须隔离、采用经验证的能量分摊，或整批积分（重叠窗口逐条积分会重复计能）。

**注意事项**：同口径比较须固定验证读回、初始化、空闲、失败和重试的纳入规则（平均功率会同时累积这些开销）。含失败／重试的整批能量除以成功交付数可另报每次成功交付的系统成本；成功样本的统计只纳入对应的有效访问窗。[10, Sec. III] [11, Sec. 4.4]

### 【结果处理和验证】

- **验证功能与计量**：读数据须正确，写须通过目标位读回、掩码和受扰位核验；确认电源、辅助和预充恢复。仿真收紧步长和电流容差，硅测重复采样并核对积分与平均功率换算，直到时序、能量和差值的不确定度满足预算。无功能结果、超时、恢复失败、无法归属能量和无法确认完成事件的样本分别登记。
- **按事务交付**：保存原始波形、宏版次、样本／事务标识、操作、PVT、初态与活动、实际访问率、位数、电源轨、$t_0,t_1$、接收／完成事件、$E_{\mathrm{tot}},E_{\mathrm{idle}},D$、通过标记和误差。不满足规格的测点保留原因；在同一有效记录计算 $ED$。
- **文献硅测对照**：Trivedi 等的 2 nm xBIT 报告 0.95 V 的 102 ps 读访问时间、同电压的 4.0 GHz 最高频率（250 ps 周期）和 0.5 V 的 0.61 μW/MHz。只在同一电压和试验配置下、确认功率归一所用的访问计数及活动后复算。[3, Figs. 15.2.6–7] Do 等的 65 nm 宏在室温、1.0 V 下报告读延时 2.2 ns；由图 27(b) 读得每次能量约 2.8 pJ，同工作点乘积约 6.2 pJ·ns。原文未提供逐事务配对数据，只能作工作点比较。[18, Sec. V, Fig. 27]

## 数据可视化与评估

按同一宏版次、操作、PVT 和验证条件分组，先对 $n$ 次配对的有效访问逐次求乘积，再统计其均值和分位数：

$$
\overline{\mathrm{EDP}}=\frac{1}{n}\sum_{i=1}^{n}E_iD_i
=\overline E\,\overline D+\frac{1}{n}\sum_{i=1}^{n}(E_i-\overline E)(D_i-\overline D).
$$

横线表示样本算术均值。批量测量若只能给出 $\overline E\,\overline D$，须标为**均值乘积**；加权读写混合工作负载采用所定义的成功访问权重 $w_{\mathrm R},w_{\mathrm W}$（无量纲，和为 1），计算 $w_{\mathrm R}\overline{\mathrm{EDP}}_{\mathrm R}+w_{\mathrm W}\overline{\mathrm{EDP}}_{\mathrm W}$，并说明该延时口径能覆盖的操作及成功率。若操作的延时不可测，须单列覆盖范围。用配对样本求乘积分位数，报告样本数、失败率和误差；多个样片或重复批次宜按独立样本组估计置信区间。缓存级文献使用的地址权重、标签和命中／未命中边界须按原口径报告。[5, Sec. VI] [14, Sec. III] [15, Sec. III, Figs. 5–10]

**规格筛选与 Pareto 前沿**：在相同容量、端口、位宽、活动、PVT 和负载下，先检查功能与良率、读写延时上限、吞吐下限、面积、待机功耗及独立能量上限，再画合格方案的 $E$–$D$ 散点与等值线 $E=C/D$（$C>0$ 为 EDP）。注明散点是单次配对值、均值或规定分位数。当另一方案在图示统计量上的能量和延时均不大于该方案且至少一项更小时，该方案在该投影中受支配。均值散点的支配关系不能代替逐次乘积的排序。扫电压时并列原始 $E,D$、恢复时间和失效率。[7, Fig. 18] [8, Figs. 19–20] [13, Figs. 16–18]

**敏感度示例（假设）**：两方案的 EDP 比为 $(E_2/E_1)(D_2/D_1)$；小相对变化下，乘积相对变化约为两项相对变化之和。以 2.00 pJ、0.80 ns 为基线，降为 1.60 pJ、1.00 ns 时，两者均为 1.60 pJ·ns；若期限为 0.90 ns，低能量方案超时，不能进入合格方案的 Pareto 前沿。

## 应用场景与指标关系

在设计与工艺协同优化（Design-Technology Co-Optimization，DTCO）中，用 EDP 比较分存储体、读摆幅、写辅助、互连和供电工作点。若最优工作点随面积约束变化，联用 [EDAP](EDAP.md)；用 [Tree Delay/Energy %](Tree_Delay_Energy_Percent.md) 和 [RD](../Subarray/Read_Delay.md)、[WD](../Subarray/Write_Delay.md) 区分全局与本地通路。树和子阵列能量只有在边界互斥时可相加；并行延时按宏实际波形提取。[4, Secs. 3–5] [5, Secs. V–VI] [6, Secs. 7.1–7.5] [13, Sec. IV, Figs. 16–19] [14, Sec. III] 与按周期表征的缓存模型比较时，保留原模型的活动分母及周期口径。[17, Sec. 4.1] [19, Sec. IV-C]

**文献对照（模型）**：Liu 等在 A14、典型角、27 °C 的 16 MB 数据宏中固定中心引脚和 H 树，图 16(a)/(b) 用相同子阵列配置给出读延时和读能量分项，图 20 给出宏 EDP；图示写失败点不参与工程选型。[13, Sec. IV, Figs. 16, 20]

Shen 等对 Ultra8T 的电压扫描中，28 nm、256 × 64 阵列的正常读后仿真在 0.4 V 得到最低读能量 1.69 pJ，在 0.45 V 得到最低读 EDP，后一点的读延时为 24.8 ns。原文边界含阵列、译码和时序模块，未计控制器与模拟电路开销；复算需读同一电压点的图 12 和图 13。[16, Sec. 5.1, Figs. 12–13]

## 参考文献

检索范围：Zotero `02-SRAM-DTCO/SRAM-Metrics/Macro`（`J7MHPUK7`），精确标签 `EDP (Energy Delay Product)`。补检前命中 3 条；补检后 18 条有可读归档全文（16 篇独立期刊／会议研究、1 份技术报告、1 部专著），另有 1 条题录。OpenRAM 固定版本网页 [2] 为补充方法。以下按原文的计算边界区分 SRAM EDP、周期口径及测量方法。

[1] R. Gonzalez and M. Horowitz, “Energy dissipation in general purpose microprocessors,” IEEE J. Solid-State Circuits, vol. 31, no. 9, pp. 1277–1284, 1996. [DOI 10.1109/4.535411](https://doi.org/10.1109/4.535411). [公开文献](https://doi.org/10.1109/4.535411)；[Zotero](https://www.zotero.org/users/7333024/items/FX6ZLTKL)。

**相关摘要：** 论文指出降低时钟频率即可降低功率，因此仅以功率比较设计容易忽略性能损失；降低电压也会在能量与速度间产生折衷。作者选择能量延迟乘积评价处理器，并讨论架构与电路开销。其原始工作负载和性能尺度属于处理器，能够支持综合指标的选择原则，但不能把处理器数值或归一化方式直接移植为SRAM访问指标。应用于本页时应把工作量固定为相同SRAM访问，采用同一工作点的访问能量与延迟相乘。原文处理器能效单位和性能评分不能原样照搬，功率延迟积也不能替代能量延迟积。

**原文定位：** §II，pp.1277–1279（PDF第1–3页）。

[2] VLSIDA, “Characterization,” OpenRAM, revision 2f7b3866418ac1ce17ad959207a1489033d8c577. [原文](https://github.com/VLSIDA/OpenRAM/blob/2f7b3866418ac1ce17ad959207a1489033d8c577/docs/source/characterization.md)；Zotero：本次检索范围内未匹配记录。

**相关摘要：** 该固定版本的官方文档说明OpenRAM用SPICE生成时序与功耗表，也支持解析模型。表征按工艺、电压、温度、输入边沿及输出负载展开，最小时钟周期通过搜索确定；内部位线、节点和感放使能检查用于验证功能。动态功耗和漏电分别处理，解析结果依赖工艺参数，不能与完整后仿真混为同一精度。其延迟表和功率表可支持综合评估，但必须在相同负载、边沿、工作角及操作窗口下配对。先将功率换成每次访问能量，再与相应访问延迟相乘；最小周期和输出传播延迟不可随意互换。

**原文定位：** 网页“Characterization Measurements”“Analytical Characterization”“Power/Delay Characterization”，固定提交2f7b386。

[3] M. Trivedi et al., “A 350mV single-rail SRAM using a custom-logic-bitcell in 2nm-CMOS-nanosheet technology for mobile and edge-AI applications,” in IEEE ISSCC Dig. Tech. Papers, paper 15.2, 2026. [DOI 10.1109/ISSCC49663.2026.11409350](https://doi.org/10.1109/ISSCC49663.2026.11409350). [公开文献](https://doi.org/10.1109/ISSCC49663.2026.11409350)；[Zotero](https://www.zotero.org/users/7333024/items/2DMRRST6)

**相关摘要：** 论文展示2 nm纳米片逻辑位单元SRAM，通过局部／全局读写通路与控制优化降低功耗，写端采用银行级时钟混合减少无效切换。宏布局、字节门控及位单元选择共同影响性能和能量，比较还依赖电源和容量条件。该文提供特定芯片架构证据，不能把单元、局部通路和整个宏的测量范围互相替换。宏能量和读取速度应在同一工作点配对，低电压最低能量不能与高电压最高速度拼成乘积。文中没有直接提供统一EDP表，本页保留其架构与测量参考，避免把密度或频率的独立改善当作EDP结论。

**原文定位：** ISSCC paper 15.2，PDF第1–3页，图15.2.2–15.2.7。

[4] S. Thoziyoor, N. Muralimanohar, and N. P. Jouppi, “CACTI 5.0,” Hewlett-Packard Laboratories, Tech. Rep. HPL-2007-167, Oct. 19, 2007. ；[Zotero](https://www.zotero.org/users/7333024/items/JYDVTQLK)；DOI：Zotero未收录或尚未核实。

**相关摘要：** 归档附件实际为2007年CACTI 5.0报告，作者为Thoziyoor、Muralimanohar和Jouppi，不能按Zotero的2008年四作者题录引用。报告将存储器分为bank、mat及子阵列，建模译码、位线、感放、复用和请求／回复树。地址与输入数据树可门控，输出树使用不同驱动结构；阵列组织搜索需同时考虑时延、功耗与布局开销。组织搜索允许以能量延迟乘积为目标，缓冲器尺寸和间距也可在能量与延迟之间折衷。用于本页需采用同一组织、工作点和访问的配对能量与延迟，并说明是否含标签及树网络，不能混乘各自最优值。

**原文定位：** §3–5，报告pp.8–27（PDF第9–28页）。

[5] D. P. Ravipati, R. Kedia, V. M. Van Santen, J. Henkel, P. R. Panda, and H. Amrouch, “FN-CACTI: advanced CACTI for FinFET and NC-FinFET technologies,” IEEE Transactions on Very Large Scale Integration (VLSI) Systems, vol. 30, no. 3, pp. 339-352, 2022. [公开文献](https://doi.org/10.1109/TVLSI.2021.3123112)；[DOI](https://doi.org/10.1109/TVLSI.2021.3123112)；[Zotero](https://www.zotero.org/users/7333024/items/XJDUBD5N)

**相关摘要：** FN-CACTI使用经商业模型校准的FinFET与负电容FinFET器件参数改进缓存估算，加入电压相关驱动、电容和互连。设计空间搜索以能量延迟乘积选择组织；研究动态电压缩放时固定在最高电压选出的布局，避免每个电压重新组织造成虚假收益。结果属于模型分析，器件参数、容量、bank数和电压应成套比较。模型以EDP筛选缓存组织，电压缩放分析随后固定布局，保证能量和延迟来自同一物理设计。引用应报告读写操作范围与动态、漏电能量构成，不能把不同电压下各自最低能量和最低延迟拼接相乘。

**原文定位：** §V–VI，pp.345–349（PDF第7–11页）。

[6] H. H. Liu, and F. Catthoor, “Circuit-technology Co-optimization of SRAM design in advanced CMOS nodes,” Cham, Springer Nature Switzerland, 2025. [公开文献](https://doi.org/10.1007/978-3-031-76109-6)；[DOI](https://doi.org/10.1007/978-3-031-76109-6)；[Zotero](https://www.zotero.org/users/7333024/items/CHVFC3IE)

**相关摘要：** 本书贯通单元、子阵列和宏级仿真。局部指标由含寄生和外围的电路得到，宏模型再加入树形互连、控制驱动及核心至数据通路；两级统计边界不可混用。先进节点的单元缩小未必等比例改善访问性能，线阻、电容和写辅助代价可能抵消收益。宏级比较采用明确容量、树形结构、引脚位置及工艺条件，并讨论写入可行性的约束。书中局部RD/RE与宏级能量、延迟属于两套层次。宏EDP必须包括相同访问的树、控制和子阵列贡献，不能把局部读能量乘宏访问延迟；技术比较还需统一容量、供电和互连假设。

**原文定位：** §2.3.2、§2.4.2、§6.2、§7.1–7.5，书内pp.36、42、137–139、174–181。

[7] B. S. Amrutur and M. A. Horowitz, “Speed and power scaling of SRAM's,” *IEEE Journal of Solid-State Circuits*, vol. 35, no. 2, pp. 175–185, 2000. [DOI 10.1109/4.823443](https://doi.org/10.1109/4.823443)；[公开文献](https://doi.org/10.1109/4.823443)；[Zotero](https://www.zotero.org/users/7333024/items/CH2EXX7I)。

**原文定位**：§IV、图 18，pp. 182–184。对同一 4 Mb、0.25 μm SRAM 的不同阵列组织进行能量与延时建模，图 18 的每个方案可作为一组 $E,D$ 比较；无逐事务硅测。

[8] M. E. Sinangil, N. Verma, and A. P. Chandrakasan, “A Reconfigurable 8T Ultra-Dynamic Voltage Scalable (U-DVS) SRAM in 65 nm CMOS,” *IEEE Journal of Solid-State Circuits*, vol. 44, no. 11, pp. 3163–3173, 2009. [DOI 10.1109/JSSC.2009.2032493](https://doi.org/10.1109/JSSC.2009.2032493)；[公开文献](https://doi.org/10.1109/JSSC.2009.2032493)；[Zotero](https://www.zotero.org/users/7333024/items/SFTQMUPB)。

**原文定位**：§V、图 19–20，pp. 3171–3172。每周期 128 bit 访问，分列漏电、切换能量和最高访问频率；频率上限不是逐次请求至数据有效的延时。

[9] N. Verma and A. P. Chandrakasan, “A 256 kb 65 nm 8T Subthreshold SRAM Employing Sense-Amplifier Redundancy,” *IEEE Journal of Solid-State Circuits*, vol. 43, no. 1, pp. 141–149, 2008. [DOI 10.1109/JSSC.2007.908005](https://doi.org/10.1109/JSSC.2007.908005)；[公开文献](https://doi.org/10.1109/JSSC.2007.908005)；[Zotero](https://www.zotero.org/users/7333024/items/94NS3U8F)。

**原文定位**：§V-B/C、图 21–22，p. 148。实测分别报告 350 mV 下的访问频率与总功率、漏电功率；可据明确活动与计数定义使用平均功率，未给同点绝对接口延时供复算。

[10] T.-H. Kim, J. Liu, J. Keane, and C. H. Kim, “A 0.2 V, 480 kb Subthreshold SRAM With 1 k Cells Per Bitline for Ultra-Low-Voltage Computing,” *IEEE Journal of Solid-State Circuits*, vol. 43, no. 2, pp. 518–529, 2008. [DOI 10.1109/JSSC.2007.914328](https://doi.org/10.1109/JSSC.2007.914328)；[公开文献](https://doi.org/10.1109/JSSC.2007.914328)；[Zotero](https://www.zotero.org/users/7333024/items/QRLTXRPI)。

**原文定位**：§III、图 16–17，p. 527。给出电压扫描下的宏功率和频率，以及按象限报告的访问时间和频率。合并前须核实总功率与所选象限延时的活动范围。

[11] M. R. Guthaus et al., “OpenRAM: An open-source memory compiler,” in Proc. IEEE/ACM ICCAD, 2016. [DOI 10.1145/2966986.2980098](https://doi.org/10.1145/2966986.2980098)；[公开文献](https://doi.org/10.1145/2966986.2980098)；[Zotero](https://www.zotero.org/users/7333024/items/DYJK5C4I)。

**原文定位**：§§3、4.4（PDF 第 3–5 页）。以宏外部端口仿真表征时序及功率，并生成时序库；复算 EDP 须保留读写激励、活动与实际访问计数。

[12] H.-H. Liu et al., “CFET SRAM DTCO, Interconnect Guideline, and Benchmark for CMOS Scaling,” *IEEE Transactions on Electron Devices*, vol. 70, no. 3, pp. 883–890, 2023. [DOI 10.1109/TED.2023.3235701](https://doi.org/10.1109/TED.2023.3235701)；[公开文献](https://doi.org/10.1109/TED.2023.3235701)；[Zotero](https://www.zotero.org/users/7333024/items/W99KL789)。

**原文定位**：§III-B/E、图 15，pp. 885–889。按操作时长积分有功能量，逐配置列读写延时和 EDP。写端采用简化固定辅助电压，未计相应专用写外围；数据属于子阵列仿真。

[13] H.-H. Liu et al., “Future Design Direction for SRAM Data Array: Hierarchical Subarray With Active Interconnect,” *IEEE Transactions on Circuits and Systems I: Regular Papers*, vol. 71, no. 12, pp. 6495–6506, 2024. [DOI 10.1109/TCSI.2024.3410518](https://doi.org/10.1109/TCSI.2024.3410518)；[公开文献](https://doi.org/10.1109/TCSI.2024.3410518)；[Zotero](https://www.zotero.org/users/7333024/items/FKMH67JE)。

**原文定位**：§IV-B/C、图 16、20（作者稿第 8–9 页）。图 16 以同一数据宏组织列读能量和读延时分项；图 20 用同配置的宏级 EDP 比较子阵列方案及后端实现，并标明写入失败风险，属于模型结果。

[14] Z. Pei et al., “Graphene-Based Interconnect Exploration for Large SRAM Caches for Ultrascaled Technology Nodes,” *IEEE Transactions on Electron Devices*, vol. 70, no. 1, pp. 230–238, 2023. [DOI 10.1109/TED.2022.3225512](https://doi.org/10.1109/TED.2022.3225512)；[公开文献](https://doi.org/10.1109/TED.2022.3225512)；[Zotero](https://www.zotero.org/users/7333024/items/HAPE4X7F)。

**原文定位**：§III、图 6–10（作者稿第 5–6 页）。模型同时比较缓存读延时、读能量（文中记为 PDP）、EDP 和 EDAP；引用须保留局部／全局互连、容量与阵列组织。

[15] Z. Pei et al., “Ultra-Scaled E-Tree-Based SRAM Design and Optimization With Interconnect Focus,” *IEEE Transactions on Circuits and Systems I: Regular Papers*, 2024. [DOI 10.1109/TCSI.2024.3438164](https://doi.org/10.1109/TCSI.2024.3438164)；[公开文献](https://doi.org/10.1109/TCSI.2024.3438164)；[Zotero](https://www.zotero.org/users/7333024/items/ADVGSHNB)。

**原文定位**：§§II–III、图 5–10（作者稿第 7–11 页）。在缓存模型中比较 E 树和 H 树，计入标签阵列、全局互连及访问概率。所得读写能量与 EDP 应按该缓存访问边界引用。

[16] S. Shen, H. Xu, Y. Zhou, M. Ling, and W. Yu, “Ultra8T: A sub-threshold 8T SRAM with leakage detection,” *Integration*, vol. 98, 102233, 2024. [DOI 10.1016/j.vlsi.2024.102233](https://doi.org/10.1016/j.vlsi.2024.102233)；[清华大学作者组全文](https://numbda.cs.tsinghua.edu.cn/papers/integration24.pdf)；[公开文献](https://doi.org/10.1016/j.vlsi.2024.102233)；[Zotero](https://www.zotero.org/users/7333024/items/RET4329K)。

**原文定位**：§5.1、图 12–13（PDF 第 7–8 页）。对同一设计在同一工作点取读能量和读延时，二者对应的仿真边界包含阵列、译码和时序模块。原文分别给最低读能量及读 EDP 所对应的电压。

[17] A. Shafaei, S. Chen, Y. Wang, and M. Pedram, “A Cross-Layer Framework for Designing and Optimizing Deeply-Scaled FinFET-Based Cache Memories,” *Journal of Low Power Electronics and Applications*, vol. 5, no. 3, pp. 165–182, 2015. [DOI 10.3390/jlpea5030165](https://doi.org/10.3390/jlpea5030165)；[公开文献](https://doi.org/10.3390/jlpea5030165)；[Zotero](https://www.zotero.org/users/7333024/items/4HZ6TIC2)。

**原文定位**：§4.1、式 (1)–(3)、图 10。缓存模型用指令相关的活动假设，由平均功率乘周期计算每周期能量，再乘周期计算 EDP；此延时变量和归一分母须按文献口径保留。

[18] A. T. Do et al., “0.2 V 8T SRAM With PVT-Aware Bitline Sensing and Column-Based Data Randomization,” *IEEE Journal of Solid-State Circuits*, vol. 51, no. 6, pp. 1487–1498, 2016. [DOI 10.1109/JSSC.2016.2540799](https://doi.org/10.1109/JSSC.2016.2540799)；[NTU 机构档案](https://hdl.handle.net/10356/84030)；[公开文献](https://doi.org/10.1109/JSSC.2016.2540799)；[Zotero](https://www.zotero.org/users/7333024/items/TFUTJSI3)。

**原文定位**：§V、图 26–27（作者稿第 10 页）。在 65 nm、256 × 128 阵列全列并行的室温硅测中，分别给出读延时及每次访问能量随供电变化；正文和图 27(b) 的 1 pJ 出现在 0.4 V，2.5 μs 则对应 0.2 V，复算须对同电压点读图。

[19] A. Shafaei and M. Pedram, “Energy-Efficient Cache Memories using a Dual-Vt 4T SRAM Cell with Read-Assist Techniques,” in *Design, Automation & Test in Europe*, 2016. [DOI 10.3850/9783981537079_0298](https://doi.org/10.3850/9783981537079_0298)；[会议原文](https://past.date-conference.com/proceedings-archive/2016/pdf/0298.pdf)；[公开文献](https://doi.org/10.3850/9783981537079_0298)；[Zotero](https://www.zotero.org/users/7333024/items/53P6ZZ32)。

**原文定位**：§IV-A/C、图 8（PDF 第 5–6 页）。用缓存模型比较带读辅助的 4T 与 6T 组织，在给定工作负载下分列能量与周期；属于每周期缓存口径。
