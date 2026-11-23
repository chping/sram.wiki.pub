# 项目术语规范

适用于正文、表格、图注、原理图及测试说明；新增术语约定先更新本文件。

- [器件端子与工艺结构](#器件端子与工艺结构)
- [器件电学与漏电机理](#器件电学与漏电机理)
- [变异、噪声与可靠性](#变异噪声与可靠性)
- [存储层级、位单元与外围电路](#存储层级位单元与外围电路)
- [位单元稳定性、读写能力与辅助技术](#位单元稳定性读写能力与辅助技术)
- [时序、波形与接口](#时序波形与接口)
- [供电管理、功耗、能量与综合指标](#供电管理功耗能量与综合指标)
- [互连寄生与电气网络](#互连寄生与电气网络)
- [版图、几何、面积与布线](#版图几何面积与布线)
- [模型、仿真、设计数据与测量提取](#模型仿真设计数据与测量提取)
- [统计分布、抽样与评估](#统计分布抽样与评估)

## 器件端子与工艺结构

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Metal-Oxide-Semiconductor Field-Effect Transistor，MOSFET | 金属氧化物半导体场效应晶体管 |  |
| N-Channel Metal-Oxide-Semiconductor Field-Effect Transistor，NMOS | N 沟道金属氧化物半导体场效应晶体管 |  |
| P-Channel Metal-Oxide-Semiconductor Field-Effect Transistor，PMOS | P 沟道金属氧化物半导体场效应晶体管 |  |
| Complementary Metal-Oxide-Semiconductor，CMOS | 互补金属氧化物半导体 |  |
| Silicon-on-Insulator，SOI | 绝缘体上硅 |  |
| Fully Depleted Silicon-on-Insulator，FDSOI／FD-SOI | 全耗尽绝缘体上硅 |  |
| Silicon-on-Thin-BOX，SOTB | 薄埋氧层绝缘体上硅 |  |
| Fin Field-Effect Transistor，FinFET | 鳍式场效应晶体管 |  |
| Tri-Gate | 三栅结构 |  |
| Gate-All-Around Field-Effect Transistor，GAA FET | 环绕栅场效应晶体管 |  |
| Nanosheet | 纳米片 |  |
| Nanowire | 纳米线 |  |
| Complementary Field-Effect Transistor，CFET | 互补场效应晶体管 |  |
| Carbon Nanotube Field-Effect Transistor，CNFET | 碳纳米管场效应晶体管 | FS 等结构前缀沿用原文标识。 |
| Gate，G | 栅端 | 可称“栅极”；“栅源电压”等惯用术语保留。 |
| Source，S | 源端 | 可称“源极”。 |
| Drain，D | 漏端 | 可称“漏极”。 |
| Body／Bulk，B | 体端 | 电气端子，与源、漏端分别表述，即使同网。 |
| Independent Back Gate | 独立背栅 |  |
| Body | 体区 | 器件沟道所在的半导体区域，须与电气端子区分。 |
| Substrate | 衬底 | 晶片衬底区域，不泛指器件体区或体端。 |
| Well | 阱 | 工艺形成的局部掺杂区域，如 N 阱、P 阱。 |
| Well Pickup | 阱抽头 |  |
| Active Area | 有源区 |  |
| Diffusion Region | 扩散区 |  |
| PN Junction | PN 结 |  |
| Front End of Line，FEOL | 前道工艺 |  |
| Middle End of Line，MEOL／Middle of Line，MOL | 中道工艺／器件中段互连 | MOL 按引用原文保留，须注明栅接触等实际路径。 |
| Back End of Line，BEOL | 后道工艺／后段互连 |  |
| Halo Doping | 晕环掺杂 |  |
| High-k Metal Gate，HKMG | 高介电常数金属栅 |  |
| Gate Work Function | 栅功函数 |  |
| Shallow Trench Isolation，STI | 浅沟槽隔离 |  |
| Well Isolation | 阱隔离 |  |
| Dielectric Isolation Wall | 介质隔离墙 |  |

## 器件电学与漏电机理

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Threshold Voltage，Vth | 阈值电压 |  |
| Dual Threshold Voltage | 双阈值 |  |
| Constant-Current Method，CC | 恒流法 |  |
| Generalized Constant Current，GCC | 广义恒流法 |  |
| Y-Function | Y 函数 |  |
| Gate Overdrive | 栅过驱动 |  |
| Body bias | 体偏置 | 体端相对源端的偏置，使用 $V_{\mathrm{BS}}$ 或 $V_{\mathrm{SB}}$ 时须注明极性。 |
| Reverse Body Bias，RBB | 反向体偏置 |  |
| Source Bias | 源偏置 |  |
| Body Effect | 体效应 |  |
| Channel Length | 沟道长度 |  |
| Effective Channel Length | 有效沟长 |  |
| Effective Width | 有效宽度 |  |
| Transfer Curve | 转移曲线 |  |
| Output Curve | 输出曲线 |  |
| Transconductance，gm | 跨导 |  |
| Conduction Current | 导电电流 | 净导电电流按各支路有符号求和，须与电荷变化项分列。 |
| Displacement Current | 位移电流 |  |
| Inversion Charge | 反型电荷 |  |
| Weak Inversion | 弱反型 |  |
| Strong Inversion | 强反型 |  |
| Linear Region／Triode Region | 线性区 |  |
| Saturation Region | 饱和区 |  |
| Channel Pinch-off | 沟道夹断 |  |
| Pinch-off Voltage | 夹断电压 |  |
| Saturation Onset Drain-to-Source Voltage，VDS,sat | 饱和区起始漏源电压 | 给定栅源、体源偏置和温度下的工作区边界，与监控点取样漏压分别记录。 |
| On-State Drain Current，Ion | 导通电流 | 规定导通偏置下的单管稳态漏端电流幅值，参考偏置与 SRAM 工作点须分列。 |
| Saturation-Bias Drain Current，Isat／Idsat | 饱和偏置漏端电流 | 规定饱和监控偏置下的单管稳态漏端电流幅值。 |
| Off-State Drain Current，Ioff | 关态漏电流 | 规定关断端压和温度下的单管直流漏端电流幅值。参考偏置与 SRAM 工作点口径须分别标记。 |
| Source/Drain Series Resistance | 源漏串联电阻 |  |
| Carrier Mobility | 迁移率 |  |
| Surface Scattering | 表面散射 |  |
| Mobility Degradation | 迁移率退化 |  |
| Velocity Saturation | 速度饱和 |  |
| Short-Channel Effect | 短沟道效应 |  |
| Drain-Induced Barrier Lowering，DIBL | 漏端诱导势垒降低 |  |
| Channel-Length Modulation | 沟道长度调制 |  |
| Subthreshold Current | 亚阈值电流 |  |
| Subthreshold Leakage | 亚阈值漏电 |  |
| Subthreshold Swing／Subthreshold Slope | 亚阈值摆幅 | 须注明采用电压对电流对数的斜率及单位。 |
| Subthreshold Factor | 亚阈值因子 |  |
| Subthreshold Hump | 亚阈值凸起 |  |
| Junction Leakage／Reverse-Biased Junction Leakage／Drain Junction Leakage | 结漏电／反偏结漏电／漏结漏电 | 源区或漏区与体区的反偏结电流，漏结漏电特指漏端分量。 |
| Generation–Recombination | 产生–复合 |  |
| Activation Energy | 激活能 |  |
| Band-to-Band Tunneling，BTBT | 带间隧穿 |  |
| Gate-Induced Drain Leakage，GIDL | 栅诱导漏极漏电 |  |
| Gate Leakage | 栅漏电 | 栅端漏电总称，具体通路按器件模型核查。 |
| Gate Tunneling Leakage | 栅隧穿漏电 | 流经漏端的分量计入漏端电流。 |
| Stack Effect | 堆叠效应 | 串联关断器件通过内部节点电位改变各管端压和漏电。 |

## 变异、噪声与可靠性

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Systematic Variation | 系统变化 |  |
| Layout-Dependent Effect，LDE | 布局相关效应 |  |
| Boundary Effect | 边界效应 | 指阵列边缘与内部布局环境造成的器件特性差异。 |
| Random Dopant Fluctuation，RDF | 随机掺杂涨落 |  |
| Line-Edge Roughness | 线边粗糙 |  |
| Polysilicon Grain Variability | 多晶硅晶粒变异 |  |
| Local Mismatch | 局部失配 |  |
| Threshold-Voltage Mismatch，ΔVth | 阈值电压失配 | 同型、同阈值选项、同几何和同测试偏置的匹配对有符号差。 |
| Current Mismatch | 电流失配 |  |
| Current-Gain Mismatch | 电流增益失配 |  |
| Pelgrom Model | Pelgrom 模型 | 同型平面管配对参数差的统计模型。 |
| SRAM Operational Mismatch，SOMM | SRAM 工作状态失配角模型 | 按单元性能灵敏度构造给定失配概率下的不利参数方向。 |
| Transient Noise | 瞬态噪声 |  |
| Random Telegraph Noise，RTN | 随机电报噪声 |  |
| Self-Heating | 自热 |  |
| Bias Temperature Instability，BTI | 偏置温度不稳定性 |  |
| Negative Bias Temperature Instability，NBTI | 负偏置温度不稳定性 |  |

## 存储层级、位单元与外围电路

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Static Random-Access Memory，SRAM | 静态随机存取存储器 |  |
| Last-Level Cache，LLC | 末级缓存 |  |
| Uniform Cache Access，UCA | 统一缓存访问 |  |
| Non-Uniform Cache Access，NUCA | 非统一缓存访问 |  |
| Tag Array | 缓存标签阵列 |  |
| Bank | 分存储体 |  |
| Mat | 阵列块 | 沿用文献命名，与分存储体和子阵列分别表述。 |
| Subarray | 子阵列 |  |
| Bitcell | 位单元 | 存储一位数据，涉及不同拓扑时须注明 6T、8T 等。 |
| Canary Cell | 哨兵单元 | 用于跟踪全局变化，须按阵列局部失配尾部校准裕量。 |
| Inverter | 反相器 |  |
| Inverter Trip Point／Inverter Switching Threshold | 反相器翻转点／反相器翻转阈值 |  |
| Latch | 锁存器 |  |
| Cross-Coupled Inverters | 交叉耦合反相器 |  |
| Negative Feedback | 负反馈 |  |
| Positive Feedback | 正反馈 |  |
| Regeneration | 再生 |  |
| Bistability | 双稳性／双稳态 |  |
| Metastable State | 亚稳态 |  |
| Pull-up，PU | 上拉管 | 常规 6T 单元中组成反相器的 PMOS。 |
| Pull-down，PD | 下拉管 | 常规 6T 单元中组成反相器的 NMOS。 |
| Access transistor／Pass-gate，PG | 访问管 | 别名 Pass Transistor／Transfer Transistor，亦称“传输管”；连接位线与存储节点，须与 CMOS 传输门区分。 |
| Cell Ratio，$\beta$ | 单元比 | 默认指平面 CMOS 尺寸比 $\beta=(W/L)_{\mathrm{PD}}/(W/L)_{\mathrm{PG}}$；驱动强度比或鳍数比须另行定义。 |
| Pull-up Ratio，$\alpha$ | 上拉比 | 默认指平面 CMOS 尺寸比 $\alpha=(W/L)_{\mathrm{PU}}/(W/L)_{\mathrm{PG}}$；驱动强度比或鳍数比须另行定义。 |
| Q／QB（$\overline{Q}$） | 存储节点／互补存储节点 | QB 与 $\overline{Q}$ 表示同一互补侧，两侧模拟电压不必严格互补。 |
| Transmission Gate | 传输门 | 须与位单元访问管区分。 |
| Wordline，WL | 字线 | 控制访问管栅端的信号线。 |
| Global Wordline | 全局字线 |  |
| Local Wordline | 局部字线 |  |
| Bitline，BL／BLB | 位线／互补位线 | BLB 中的 B 表示互补侧，不表示体端。 |
| Hierarchical Bitline | 层次位线 |  |
| Global Bitline | 全局位线 |  |
| Local Bitline | 局部位线 |  |
| Replica Bitline | 复制位线 |  |
| Predecoding | 预译码 |  |
| Row Decoder | 行译码器 |  |
| Column Decoder | 列译码器 |  |
| Wordline Driver／WL Driver | 字线驱动 |  |
| Write Driver | 写驱动 |  |
| Multiplexer，MUX | 多路选择器 | 列复用器为其位线列选择用途。 |
| Column Multiplexer／Column MUX | 列复用器 |  |
| Output Buffer | 输出缓冲 |  |
| Precharge | 预充电 |  |
| Precharge Transistor | 预充管 |  |
| Equalization | 均衡 |  |
| Equalization Transistor | 均衡管 |  |
| Reset | 复位 |  |
| Reset Transistor | 复位管 |  |
| Keeper | 保持器 |  |
| Sampling Switch | 采样开关 |  |
| Sampling Aperture | 采样孔径 |  |
| Kickback／Sampling Kickback | 反冲／使能反冲／采样反冲 | 须注明采样或使能切换事件及受扰输入端口。 |
| Analog-to-Digital Converter，ADC | 模数转换器 |  |
| Digital-to-Analog Converter，DAC | 数模转换器 |  |
| Sense Amplifier，SA | 感测放大器 | 可简称“感放”。 |
| Dynamic-Latch Sense Amplifier | 动态锁存式感测放大器 |  |
| Current-Latched Sense Amplifier，CLSA／Current-Latch Differential Sense Amplifier | 电流锁存型感测放大器 |  |
| Voltage-Latched Sense Amplifier，VLSA／Voltage-Latch Differential Sense Amplifier | 电压锁存型感测放大器 |  |
| Tail Transistor | 尾管 |  |
| Sense Amplifier Enable，SAE | 感测放大器使能 |  |
| Common-Mode Voltage | 共模电压 |  |
| Charge Sharing | 电荷共享 |  |
| Charge Injection | 电荷注入 |  |
| Sense Signal | 位线建差信号 | 指两条位线建立的电压差信号。 |
| Bitline Swing | 位线摆幅 |  |
| Sense-Amplifier Input-Referred Offset Voltage／SA Offset | 感测放大器输入等效失调电压 | 固定参考条件下稳定输出翻转的有符号输入差分，须与失调标准差及时限判决门槛区分。 |
| Hysteresis | 滞回 |  |
| Offset Calibration | 失调校准 |  |
| Capacitive Offset Correction | 电容失调校正 |  |
| Threshold-Voltage Storage | 阈值存储 | 保存器件阈值信息以减轻后续感测失配。 |
| Sense Margin Threshold | 目标位线建差门槛 | 由感放失调、共模电压、噪声及访问时限共同确定。 |
| Sense-Amplifier Decision Threshold／SA Decision Threshold | 感测放大器判决门槛 | 固定截止、连续有效窗口及目标失效率下的最小输入差分幅度，区别于有符号参考失调。 |
| Regeneration Time Constant | 再生时间常数 | 再生初期共模与增益近似恒定时，小信号差分指数增长的时间常数。 |
| Sensing Window | 感测窗口 |  |
| Decision Deadline | 判决截止时刻 | 相对本地 SAE 固定，延长诊断观察不改变工作判定。 |
| Output Validity Window | 连续有效窗口 | 正确输出须在截止前的完整规定窗口内连续有效。 |
| Wrong Decision | 错判 | 规定连续有效窗内为反向输出。 |
| Late Decision | 迟判 | 仅在诊断期内达到完整正确有效窗口，仍计工作失效。 |
| Unresolved Decision | 未决 | 诊断结束仍未达到完整正确有效窗口。 |
| Output Hold Failure | 输出保持失效 | 违反规定的截止后保持要求，须与位单元数据保持失效区分。 |
| Read Access Failure | 读访问失败 | 规定感测窗口内正确位线压差不足或感放判决错误。 |
| Sense-Amplifier Standby Current，I_SA,stby | 感测放大器待机电流 | 规定待机状态稳定后指定供电端口的电流。须注明供电轨和单路或共享域边界。 |

## 位单元稳定性、读写能力与辅助技术

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Bitcell Read Current／Read Current，Iread／Icell | 位单元读电流 | 从位线流入单元为正。DC、瞬态、窗口平均及本征口径须注明条件。 |
| Net Discharge Current | 净放电电流 | 观察端全部支路形成的净放电电流。 |
| Differential Effective Current | 差分有效电流 | 两条位线净放电电流之差，须注明差分极性。 |
| Pairwise Sampling | 成对采样 | 同一位单元两种存储状态下的两侧放电电流配对采样。 |
| Voltage Acceleration Method | 电压加速法 | 通过跨偏置映射重建读电流低尾。 |
| Read Disturb／Dynamic Read Disturb | 读扰动／动态读扰动／读扰 | 动态读扰动以原存储状态翻转判定。 |
| Destructive Read | 破坏性读取 |  |
| Static Read Stability Failure | 静态读稳定性失效 | 给定读偏置下原稳定工作点消失。 |
| Half-Select | 半选 |  |
| Half-Select Disturb | 半选扰动 |  |
| Voltage Transfer Characteristic，VTC | 电压传输特性 | 反相器稳态输入与输出电压的关系，须与器件转移曲线区分。 |
| Butterfly Method／Butterfly Plot／Butterfly Curve | 蝴蝶法／蝴蝶图／蝴蝶曲线／蝶形曲线 | 两侧 VTC 叠合。读／保持取叶瓣最大内接方形，写取旧态侧最小临界方形。 |
| Static Noise Margin，SNM | 静态噪声容限 | 须注明保持、读或写偏置。 |
| Hold Static Noise Margin，HSNM | 保持静态噪声容限 | 规定待机偏置下，两瓣最大内接正方形边长的较小值。 |
| Read Static Noise Margin，RSNM | 读静态噪声容限 | 固定读偏置下，两瓣最大内接正方形边长的较小值。 |
| Write Static Noise Margin／Write Noise Margin，WSNM／WNM | 写静态噪声容限 | 固定互补位线写偏置下旧态侧两条 VTC 之间的最小临界正方形边长。 |
| N-Curve Method | N 曲线法 | 闭环扫描单个存储节点，保留扫描电压与注入电流。 |
| Static Voltage Noise Margin，SVNM | 静态电压噪声容限 | N 曲线中低电位稳态零点至相邻亚稳态零点的电压差。 |
| Static Current Noise Margin，SINM | 静态电流噪声容限 | N 曲线相同两零点之间的正注入电流峰值。 |
| Write Trip Voltage，WTV | 写入翻转电压 | 读偏置 N 曲线高电位稳态至相邻亚稳态的电压差 VC−VB。 |
| Write Trip Current，WTI | 写入翻转电流 | N 曲线 B、C 间的电流极值，须注明注入方向与符号。 |
| Write-Bias Current | 写偏置电流 | 实际互补位线写偏置下的电流指标，与读偏置 WTI 区分。 |
| Word-Line Write Margin，WM／WLWM／CWLM／WLVM | 字线写入裕量 | 按原文区分准静态扫压与规定写周期下的 WLVM。 |
| Wordline Write Trip Voltage，WWTV | 字线写入翻转电压 | 部分文献指临界字线电压，Guo 等指参考电平与临界值之差，须注明报告量。 |
| Bitline Write Trip Voltage／Bitline Write Margin，BWTV／BLWM | 位线写入翻转电压／位线写裕量 | 固定字线及写高侧位线时，写低侧位线允许的最高可写电压。 |
| Closed-Loop Feedback Perturbation | 闭环反馈扰动 | 在两条反馈线上串入等幅反极性直流电压源，验证静态失稳边界。 |
| Equilibrium Branch Continuation | 平衡支路延拓 |  |
| Local Stability Analysis | 局部稳定性分析 |  |
| Basin of Attraction | 吸引域 | 写偏置撤销后，节点状态须落入目标保持状态的吸引域。 |
| Minimum Operating Voltage，Vmin／Read Vmin／Write Vmin | 最低工作电压／最低读取工作电压／最低写工作电压 | 须注明读或写模式、目标时序及完整功能判据。 |
| Data Retention Voltage，DRV | 数据保持电压 | 规定待机偏置下维持原存储态的最低局部供电压差。静态与功能 DRV 须注明测试口径。 |
| Macro Minimum Retention Voltage，Retention Vmin | 宏保持最低电压 | 规定宏端口参考点、读回、纠错配置及目标失效率下的最低外部保持供电。 |
| Data Retention Failure／Hold Failure | 数据保持失效 |  |
| Supply Voltage Guardband | 供电裕量 | 供电与保持电压边界之间的间隔，须与反馈噪声容限区分。 |
| Supply Voltage Sweep | 供电扫描 | 本页以单元供电扫描提取读稳定性代理量。 |
| Supply Read Retention Voltage，SRRV | 供电读保持电压 | 供电扫描得到的读稳定性代理量，须与蝴蝶法 RSNM 区分。 |
| Wordline Read Retention Voltage | 字线读保持电压 | 字线电压扫描得到的读稳定性代理量。 |
| Dynamic Stability／SRAM Dynamic Stability | 动态稳定性／SRAM 动态稳定性 |  |
| Dynamic Hold Noise Margin | 动态保持噪声容限 | 须注明扰动幅度、脉宽及恢复判据。 |
| Critical Charge | 临界电荷 |  |
| Soft Error | 软错误 |  |
| Dynamic Write Margin | 动态写裕量 | 可用字线脉宽减临界写脉宽，须固定写后判据。 |
| Assist Circuits | 辅助电路 | 通过调整偏置或时序改善读写性能或裕量。 |
| Write Assist | 写辅助 | 按功能目标分类：改善写裕量或降低写 $V_{\min}$。 |
| Read Assist | 读辅助 | 按功能目标分类：改善读稳定性或读取速度，须注明具体目标。 |
| WL Assist | 字线辅助 | 按作用端口分类：调整 WL 电压或波形；须注明读／写目标及实际电压。 |
| WL Overdrive／Boost | 字线助推 | 选通高电平高于 $V_{\mathrm{DD}}$，增强 PG 驱动，常用于写辅助。 |
| WL Underdrive／Lowering | 字线降压 | 选通高电平低于 $V_{\mathrm{DD}}$，常用于抑制读扰动。 |
| BL Assist | 位线辅助 | 按作用端口分类：调整 BL/BLB 偏置或时序；须注明读／写目标及实际电压。 |
| Negative Bitline，NBL | 负位线辅助 | 写入期间使放电侧位线电位低于 $V_{\mathrm{SS}}$，增强写入能力。 |
| BL Precharge Lowering | 位线预充降压 | 将位线预充目标设为低于 $V_{\mathrm{DD}}$，常用于读稳定性辅助。 |
| BL Predischarge | 位线预放电 | 读访问前主动降低位线电位，小幅预放电亦称“微放电”。 |
| Cell VDD Lowering／Collapse | 单元电源降压辅助 | 写入期间暂时降低单元供电，削弱锁存器保持能力。 |
| Read-Port Decoupling／Read Isolation | 读端口解耦／读隔离 | 使读通路与存储节点隔离。 |
| Dynamic Write-Back | 动态回写 |  |

## 时序、波形与接口

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Propagation Delay | 传播延时 | 库表征的半幅至半幅口径须与输出有效延时分列。 |
| Transition Time／Rise Time／Fall Time | 转换时间 | 上升与下降分别注明测点及电压门限。 |
| Wordline Slew／WL Slew | 字线转换时间 | 同一局部测点、同一边沿两个指定电压门限间的时间，单位 s。 |
| Average Slew Rate／Slew Rate | 转换速率 | 区间平均值为电压差除以转换时间，单位 V/s。 |
| Duty Cycle | 占空比 |  |
| Overshoot | 过冲 |  |
| Undershoot | 下冲 |  |
| Critical Path／Critical Causal Path | 关键路径／关键因果路径 | 实际决定访问完成时刻的因果链，树时间按同一访问窗内非重叠传播区间计量。 |
| Replica Path | 复制时序路径 |  |
| Wordline Arrival Delay | 字线到达延时 | 从指定控制端到局部栅端对应交越的时间差，须注明触发端、极性及门限。 |
| Wordline Pulse Width／WL Pulse Width | 字线脉宽 | 半幅脉宽与功能有效脉宽须分别注明门限及判据。 |
| Critical Write Wordline Pulse Width／Critical Write Pulse Width | 临界写字线脉宽 | 规定写有效期限、保持及读回条件下，最短成功的局部字线脉宽。 |
| Critical Read Wordline Pulse Width | 临界读字线脉宽 | 最短能正确读出的字线脉宽，为依赖感放和真实边沿的功能代理量。 |
| Usable Activation Window | 可用选通窗口 | 功能判据连续成立且与读建差或写位线有效窗口重叠的时间。 |
| Minimum Functional Write Window | 最小功能写窗口 | 按实际扫描的接口量提取，须注明读回间隔及功能判据。 |
| Non-Overlapping Timing | 非重叠时序 |  |
| Read Develop Time | 读位线建差时间 | 局部字线上升半幅至感放输入正确差分达到门槛并保持至采样参考的时间。 |
| Subarray Read Delay／Read Delay／Read Access Delay，RD | 子阵列读延时 | 本地接口接受指定读命令至带规定负载的本地输出持续有效的时间。 |
| Macro Read Delay | 宏接口读延时 | 宏端口接受请求至宏数据端有效的时间。 |
| Cache Access Time | 缓存访问时间 | 缓存请求至数据和命中状态可供使用的时间。 |
| Minimum Read Cycle Time | 最小读周期 | 相邻两次合法读命令可被接受的最短间隔。 |
| Local Write Time／Write Time | 局部写入时间 | 给定写波形下，局部字线上升半幅至双节点持续达到目标电平的时间。 |
| Subarray Write Delay／Write Delay，WD | 子阵列写延时 | 本地接口接受写请求至选中位双节点持续达到目标电平并经写后验证的时间。 |
| Macro Write Delay，Internal Write Delay | 宏写延时／内部写延时 | 宏接口延时与内部节点稳定延时须按各自起止事件分别报告。 |
| Write Recovery | 写后恢复 | 分别记录单元保持条件恢复及位线预充均衡。 |
| Readback | 读回 |  |
| Same-Value Write／Same-Value Rewrite | 同值写 | 写入数据与原存储数据相同，仍可能激活写驱动、字线、位线及预充。 |
| Input/Output，I/O | 输入／输出 |  |
| Synchronous Interface | 同步接口 |  |
| Handshake Interface | 握手接口 |  |
| Setup Time | 建立时间 |  |
| Hold Time | 保持时间 |  |
| Clock Skew | 时钟偏斜 |  |
| Timing Jitter | 抖动 |  |
| Write Enable | 写使能 |  |
| Write Mask | 写掩码 | 控制多位写入中实际允许更新的位。 |
| Tri-State Output | 三态输出 |  |
| Write Acknowledge，ACK | 写确认 | 协议事件。作为 WD 代理前须校准其与双节点状态有效事件的关系。 |

## 供电管理、功耗、能量与综合指标

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| VDD | VDD| 高电位电源网，一般不翻译为中文。电位记为 $V_{\mathrm{DD}}$，供电压差为 $V_{\mathrm{DD}}-V_{\mathrm{SS}}$。 |
| VSS | VSS | 低电位或参考电源网，一般不翻译为中文。电位记为 $V_{\mathrm{SS}}$，仅在声明 $V_{\mathrm{SS}}=0$ 时，供电压差才可简写为 $V_{\mathrm{DD}}$。 |
| GND | 地／参考节点 | 仅在明确同网时与 VSS 等同。 |
| Power Domain | 电源域 |  |
| Power-Domain Isolation | 跨电源域隔离 |  |
| Level Shifter | 电平转换器 |  |
| Back-Powering | 反向供电 | 仍上电的外部域经接口或钳位向关断域供电。 |
| Data Retention／Retention Mode／Hold Mode | 数据保持／保持模式 | 保留原数据的供电模式。 |
| Sleep Mode | 睡眠模式 | 须注明睡眠模式是否保留数据及实际供电状态。 |
| Retention Voltage Scaling | 保持电压缩放 |  |
| Power Gating | 电源门控 |  |
| Power Switch／Sleep Transistor | 电源开关／睡眠管 | 睡眠管为控制睡眠或保持供电的晶体管开关。 |
| Virtual Supply | 虚拟电源 |  |
| Virtual Ground | 虚拟地 |  |
| Wake-Up Latency | 唤醒延时 | 须注明睡眠退出命令和恢复有效功能的判据。 |
| Voltage Regulator | 稳压器 |  |
| Charge Pump | 电荷泵 |  |
| Decoupling Capacitor | 去耦电容 |  |
| Power Supply Ripple | 供电纹波 |  |
| Clock Gating | 时钟门控 |  |
| Output Gating | 输出门控 |  |
| Data Gating | 数据门控 |  |
| Byte Gating | 字节门控 |  |
| Standby Power | 待机功耗 | 同一电路边界各外部端口电压与流入电流乘积之和。 |
| Bitcell Standby Leakage Current／Standby Leakage | 位单元待机漏电流 | 从单元 VDD 流入的保持态电流。位线与体偏置端另报，并注明 DC、瞬态或窗口平均口径。 |
| Intrinsic Leakage | 本征漏电 | 在隔离外部阵列负载的完整位单元上表征，保留各端口漏电路径。 |
| Dynamic Power | 动态功耗 |  |
| Short-Circuit Current | 短路电流 |  |
| Dynamic Energy | 动态能量 |  |
| Subarray Read Energy／Read Energy，RE | 子阵列读能量 | 完整计量窗口内按成功读事务归一化，分别报告总能量与扣待机基线的增量能量。 |
| Subarray Write Energy／Write Energy，WE | 子阵列写能量 | 按成功写事务归一化，分别报告总能量与扣待机基线的增量。须与写使能信号 WE 区分。 |
| Waveform Integration | 波形积分 |  |
| Trapezoidal Integration | 梯形积分 |  |
| Average-Power Method | 平均法 | 用同窗平均功率与成功事务率折算单次访问能量。 |
| Actual Access Rate | 实际访问率 | 同一计量窗口内按规定计数规则得到的访问次数除以窗口时长，须与时钟频率区分。 |
| Energy Attribution | 能量归属 | 按互斥供电支路或经校准的共享分摊，将能量计入所属功能域。 |
| Unattributed Energy Residual | 未归属能量残差 | 宏总供电能量减去已归属树与非树能量的有符号差，禁止直接计为树能量。 |
| Global Access-Tree Delay and Energy Shares | 全局访问树延时与能量占比 | 同次成功宏访问中分别计量关键路径树时间占比与就绪至就绪窗内树供电能量占比。 |
| Energy–Delay Product，EDP | 能量延时积 | 同次有效访问的供电能量与访问延时之积，宏级默认使用完整访问窗总能量。 |
| Energy–Delay–Area Product，EDAP | 能量延时面积积 | 同次有效宏访问的能量、延时与完整宏占地之积，工程单位为 J·s·μm²。 |
| Power–Delay Product，PDP | 功率延时积 | 平均功率与延时之积，单位 J。功率在同一延时窗口内取平均时等于该窗能量。 |
| Power–Delay–Area Product，PDAP／PAD | 功率延时面积积 | 使用平均功率构成，与每次访问能量构成的 EDAP 分别报告。 |
| Power, Performance and Area，PPA | 功耗、性能与面积 |  |
| High Performance，HP | 高性能 |  |
| High Density，HD | 高密度 |  |
| Low Power，LP | 低功耗 |  |
| Design-Technology Co-Optimization，DTCO | 设计技术协同优化 |  |
| Pareto Frontier／Pareto Front | Pareto 前沿 | 须先筛选功能与规格，再按全部评价维度判定非支配候选。 |

## 互连寄生与电气网络

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Resistance and Capacitance，RC | 电阻与电容 |  |
| Distributed Resistance and Capacitance，Distributed RC／RC Ladder Network | 分布 RC／分布电阻电容／RC 梯形网络 |  |
| Lumped Approximation | 集总近似 |  |
| Pi-Section RC Model | π 型 RC 模型 |  |
| RC Tree | RC 树 |  |
| Time Constant | 时间常数 |  |
| Elmore First Moment | Elmore 一阶矩 | 线性 RC 树的响应一阶矩，须与指定阈值的延时区分。 |
| Network Reduction | 网络约简／网络降阶／降阶网络 |  |
| Equivalent Resistance | 等效电阻 | 须注明注流、感测端口及其余端口终端，与每节距值分列。 |
| Line Resistance | 主线电阻 | 主线两端参考面之间的端到端等效电阻，须与抽头支路区分。 |
| Tap Resistance | 抽头支路电阻 | 主线抽头至器件端子参考面之间的电阻，须注明所属网络及端子路径。 |
| Gate Resistance | 栅电阻 | 须区分紧凑模型内栅电阻与外部栅支路电阻。 |
| On-Resistance | 导通电阻 |  |
| Contact Resistance | 接触电阻 |  |
| Specific Contact Resistivity | 比接触电阻率 | 须与单位为 Ω 的接触电阻区分。 |
| Effective Resistivity | 有效电阻率 |  |
| Current Crowding | 电流拥挤 |  |
| Small-Signal Resistance Matrix／Resistance Matrix | 小信号电阻矩阵 | 须注明稳定工作点、端口回流参考及其余端口终端。 |
| Driving-Point Resistance／Self Resistance | 驱动点电阻／自电阻 | 指定终端条件下电阻矩阵的对角项。 |
| Transfer Resistance | 传输电阻／转移电阻 | 指定终端条件下电阻矩阵的非对角项。 |
| Cross-Bridge Kelvin Resistor，CBKR | 交叉桥开尔文电阻／交叉桥 Kelvin 测试结构 | 用于测量指定参考面之间的低接触电阻。 |
| Via Chain／Contact Chain | 通孔链／接触链 | 用于组合互连电阻测量与异常定位的串接测试结构。 |
| Geometric Capacitance | 几何电容 | PEX 网络中的对参考导体电容与导体间耦合电容，须与带器件端口有效电容区分。 |
| Ground Capacitance | 对参考节点电容 | 几何寄生分量。可按约定合入固定交流电位导体的贡献，须注明参考节点。 |
| Coupling Capacitance | 耦合电容 | 两个保留导体之间的正值几何电容，区别于随邻线波形变化的端口有效电容。 |
| Capacitive Coupling | 电容耦合 |  |
| Shielding | 屏蔽 |  |
| Fringing Capacitance | 边缘电容 |  |
| Gate Overlap Capacitance | 栅端重叠电容 |  |
| Junction Capacitance | 结电容 |  |
| Gate Capacitance／Differential Gate Capacitance | 栅电容／微分栅电容 | 微分值在其他端子固定时由栅端电荷导数取得。 |
| Port Effective Capacitance／Effective Capacitance／Switching Effective Capacitance | 端口有效电容／有效电容／开关等效电容／电荷等效电容 | 由指定偏置、邻线终端、频率或充电窗口下的端口响应取得，不能直接视为独立几何电容。 |
| Capacitance Matrix | 电容矩阵 |  |
| Port Admittance／Multiport Admittance | 端口导纳／多端导纳 | 多端提取中以流入网络为正，记录端口电流增量与激励电压增量之比。 |
| Port Impedance | 端口阻抗 | 频率响应为复阻抗，须注明参考面及计入的上游网络。 |
| Source Impedance | 源阻抗 |  |
| Reciprocity | 互易性 |  |
| Kirchhoff's Current Law，KCL | 基尔霍夫电流定律 |  |
| Bitcell-Pitch Bitline Resistance and Capacitance，CELL_BL RC | 单元节距位线寄生 | 沿列方向跨一个铺排节距的增量电阻和电容，须注明是否含访问管端子电容。 |
| Subarray Bitline Resistance and Capacitance／Bitline Resistance and Capacitance，BL RC | 子阵列位线电阻与电容／位线 RC | 列端至各位单元抽头的整列分布寄生网络，须与单元节距增量区分。 |
| Bitline Leakage Current／Bitline Leakage／BL Leakage | 位线漏电流 | 规定数据、偏置及边界下维持 BL／BLB 端电位的两路稳态有符号电流，流入列为正。 |
| Sneak Leakage Paths | 潜漏电路径 |  |
| Backflow Current | 回灌电流 | 从列回流到钳位源时，按本文列端方向取负。 |
| Empty-Column Reference | 空列对照 | 移除位单元支路，并匹配列线、测量通路及外围端压与控制。 |
| Leakage-Induced Bitline Voltage Drop | 漏电所致位线压降 | 电压代理量，换算平均净电流须固定窗口并校准电荷模型。 |
| Bitcell-Pitch Wordline Resistance and Capacitance，CELL_WL RC | 单元节距字线寄生 | 沿行方向跨一个列节距的主线电阻与电容增量，栅支路电阻及访问管栅负载须分别记录。 |
| Subarray Wordline Resistance and Capacitance／Wordline Resistance and Capacitance，WL RC | 子阵列字线电阻与电容／字线 RC | 局部驱动器输出参考面至整行各访问管栅端的分布网络，须与单元节距增量区分。 |
| Wordline Segmentation | 字线分段 | 各段须计入局部缓冲器及全局选择路径。 |
| Power Delivery Network，PDN | 供电网络 |  |
| Power Rail | 电源轨 |  |
| Buried Power Rail，BPR | 埋入式电源轨 |  |
| Backside Power Rail | 背面电源轨 |  |
| Frontside Power Delivery | 正面供电 |  |
| Backside Power Delivery | 背面供电 |  |
| Bitcell-Pitch Supply-Rail Resistance，CELL_R_VDD／CELL_R_VSS | 单元节距电源轨电阻／沿轨节距电阻 | 沿 VDD 或 VSS 局部电源轨跨一个位单元节距的直流电阻增量。 |
| Subarray VDD/VSS Effective Resistance，R_VDD／R_VSS | 子阵列 VDD／VSS 等效电阻／子阵列端口电阻 | 指定馈电终端、注流端与感测端下的直流响应，须与节距电阻和运行压降分列。 |
| IR Drop | 电阻性压降 | 电流流经电阻引起的电压降。 |
| Buried Interconnect | 埋入式布线／埋入式导线 |  |
| Buried Bitline，BBL | 埋入式位线 |  |
| Active Interconnect，AIC | 有源互连 |  |
| Low-Swing Wire／Low-Swing Interconnect | 低摆幅互连 |  |
| Global Access Tree | 全局访问树 | 跨分存储体或子阵列的地址、控制、写数据分发和读数据返回网络，含归属驱动及分支缓冲。 |
| H-Tree | H 树 |  |
| E-Tree | E 树 |  |
| Repeater | 中继缓冲器 |  |
| Buffer Insertion | 缓冲插入 |  |

## 版图、几何、面积与布线

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Bitcell Area／Cell Area | 单元版图面积 | 合法周期铺排中每个物理存储位分摊的平面占地。 |
| Bitcell Height and Width／Cell Height and Width／Bitcell Pitch／Cell Pitch | 位单元高度与宽度／位单元节距 | 注明 WL／BL 方向、放置边界和周期，几何尺寸与重复节距分别定义。 |
| Aspect Ratio | 纵横比 | 须注明宽高方向及比值顺序。 |
| Minimum Repeating Tile | 最小完整重复块 | 包含完整镜像、错位及共享结构的最小重复周期。 |
| Ideal Tiling Density | 理想铺排密度 | 单元版图面积的倒数。 |
| Physical Array | 物理阵列 | 包含实际存储位点、周期插入结构、边缘结构及阵列内间隔。 |
| Array Area／Array Footprint | 阵列占地 |  |
| Physical Array Gross Density | 物理阵列毛密度 | 实际存储位数除以物理阵列占地。 |
| Macro Area／Macro Footprint／Macroblock Area | 宏面积 | 包含物理阵列、外围、宏内布线通道及边界留量。 |
| Effective Macro Density | 宏有效密度 | 用户可用数据位数除以宏占地。 |
| Die Area | 芯片总面积 | 须与可放置宏面积分别报告。 |
| Scribe Line | 切割道 |  |
| Hierarchical Layout | 层次化版图 |  |
| Placement Boundary | 放置边界 | 须与几何图形的外接框区分。 |
| Placement Halo | 放置留白 | 宏外预留空间，计入面积时须单列边界及尺寸。 |
| Routing Blockage | 禁布区 |  |
| Critical Dimension，CD | 临界尺寸 | 须与铺排重复节距区分。 |
| Fin Pitch | 鳍间距 |  |
| Contacted Poly Pitch，CPP | 接触栅距 |  |
| Gate Extension | 栅延伸 |  |
| Lambda-Based Design Rules | λ 规则 | 以最小特征尺寸 λ 表示版图几何约束。 |
| Enclosure Rule | 图形包围规则 |  |
| Design Rule Check，DRC | 设计规则检查 |  |
| Layout Versus Schematic，LVS | 版图与网表一致性检查 |  |
| Multiple Patterning | 多重图形化 |  |
| Gate Cut | 栅切割 |  |
| Fin Cut | 鳍切割 |  |
| Metal Cut | 金属切割 |  |
| Overlay Error | 套刻偏差 |  |
| WL Strap | 字线绑扎带／字线跨接／字线跨接单元 |  |
| Dummy Structure | 虚设结构 | 注明版图虚设或空白校准结构的用途及连接。 |
| Contact | 接触孔 |  |
| Contact Merging | 接触合并 |  |
| Pad | 焊盘 |  |
| Via | 通孔／过孔 |  |
| Via Cut／Cut | 开孔 | 通孔实例内的实际开孔，与通孔实例分别计数。 |
| Via Array | 通孔阵列 |  |
| Stacked Via | 叠层通孔 | 按各物理层对分别计数。 |
| Supervia | 高通孔 |  |
| Through-Silicon Via，TSV | 硅通孔 |  |
| Nano Through-Silicon Via，nTSV | 纳米硅通孔 |  |
| Global Routing | 全局布线 |  |
| Half-Perimeter Wirelength，HPWL | 半周长线长 | 引脚代表点外接矩形的宽与高之和，用于布局阶段估算。 |
| Rectilinear Steiner Minimal Tree，RSMT | 直角斯坦纳最小树 | 考虑共享分支的正交连线估算。 |
| Routing Track／Metal Track | 布线轨道 |  |
| Track Assignment | 轨道分配 |  |
| Detailed Routing | 详细布线 |  |
| Pin Access | 引脚接入 |  |
| Macro Interconnect Length and Routed Metal Area／Interconnect Length & Area | 宏级互连长度与布线面积 | 统计宏边界内已布线导线的几何，通孔及非信号网分列。 |
| Actual Routed Centerline Length | 实际布线中心线长度 | 同网同层共线重叠段只计一次，跨层分别计长。 |
| End-to-End Path Length | 端到端路径长度 | 沿实际连通路径累计，共享干线可出现在多个端到端结果中。 |
| Access-Weighted Average Wirelength | 访问加权平均线长 | 按访问概率加权路径长度，与物理网络总长分列。 |
| Per-Layer Routed Metal Area | 同层布线面积 | 按所选物理导体的同层俯视多边形并集计量。 |
| Sum of Layer Areas | 各层面积总和 | 不同层间的投影重叠仍分别计入。 |
| Planar Coverage Area | 平面覆盖面积 | 所选层投影到同一平面后的并集面积。 |
| Metal Fill | 金属填充 | 未连接填充与信号金属面积分列。 |
| Metal Area Density／Metal Density | 金属占用率 | 各层所选金属面积除以窗口与宏边界相交的面积。 |
| Planar Coverage Ratio | 跨层平面覆盖率 | 以各层投影并集面积除以同一统计窗口面积。 |

## 模型、仿真、设计数据与测量提取

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Process Design Kit，PDK | 工艺设计套件 |  |
| Memory Compiler | 存储器编译器 |  |
| Process, Voltage and Temperature，PVT | 工艺、电压和温度 |  |
| Process Corner | 工艺角 |  |
| Typical-Typical，TT | 典型工艺角 |  |
| Slow–Slow，SS | 慢慢工艺角 |  |
| RC Corner | RC 角 |  |
| Compact Model | 紧凑模型 |  |
| Berkeley Short-Channel IGFET Model，BSIM3／BSIM4 | BSIM 模型 | BSIM3、BSIM4 为同一模型族的不同版本。 |
| Berkeley Short-Channel IGFET Model–Common Multi-Gate，BSIM-CMG | BSIM-CMG 模型 |  |
| Penn State–Philips Model，PSP | PSP 模型 |  |
| Predictive Technology Model，PTM | 预测技术模型 |  |
| Technology Computer-Aided Design，TCAD | 技术计算机辅助设计 |  |
| Simulation Program with Integrated Circuit Emphasis，SPICE | SPICE |  |
| Logical Effort | 逻辑努力 |  |
| Netlist | 网表 | 禁止使用“网本”等误译。 |
| GDSII | GDSII 版图格式 |  |
| Open Artwork System Interchange Standard，OASIS | OASIS 版图格式 |  |
| Database Unit，DBU | 数据库单位 | 版图数据库坐标对应的长度标度。 |
| Library Exchange Format，LEF | 库交换格式 |  |
| Design Exchange Format，DEF | 设计交换格式 |  |
| Standard Parasitic Exchange Format，SPEF | 标准寄生交换格式 |  |
| Liberty | Liberty 时序库 |  |
| Parasitic Extraction，PEX | 寄生参数提取 |  |
| Post-Layout Simulation | 后仿真 |  |
| Direct Current，DC | 直流 |  |
| Alternating Current，AC | 交流 |  |
| Direct-Current Operating Point | 直流工作点 |  |
| Bias Sweep | 偏置扫描 |  |
| Quasi-Static Sweep | 准静态扫描 |  |
| Transient Analysis | 瞬态分析 |  |
| Frequency Sweep | 频率扫描 |  |
| Process Control Monitor，PCM | 工艺控制监测 |  |
| Test Key | 硅片测试结构 | 须区分测试结构面积与目标位单元铺排面积。 |
| Cell Under Test，CUT | 被测单元 |  |
| Universal Test Structure，UTS | 通用测试结构 |  |
| Built-In Self-Test，BIST／Memory Built-In Self-Test，MBIST | 内建自测试 | MBIST 特指存储器内建自测试。 |
| Checkerboard Pattern | 棋盘图样 |  |
| Ring Oscillator，RO | 环形振荡器 |  |
| Semiconductor Parameter Analyzer | 半导体参数分析仪 |  |
| Source Measure Unit，SMU | 源测量单元 |  |
| Automatic Test Equipment，ATE | 自动测试设备 |  |
| Nanoprobe | 纳米探针 |  |
| Scanning Electron Microscope／Scanning Electron Microscopy，SEM | 扫描电子显微镜／扫描电子显微成像 | Microscope 指设备，Microscopy 指成像方法。 |
| Pitch Standard | 节距标样 |  |
| Field-of-View Distortion | 视场畸变 |  |
| On-Chip Sampler | 片上采样器 |  |
| Shunt Resistor／Four-Terminal Shunt Resistor | 分流器／四端分流器 |  |
| Electrical Reference Plane | 电气参考面 | 限定提取或测量网络的电气边界。 |
| Kelvin Connection／Four-Wire Sensing／Force/Sense | 开尔文四线测量 | 激励与感测通路分离，须注明四端连接参考点。 |
| Multiport AC Extraction | 多端交流提取 | 逐个激励端口、固定其余独立端口的小信号电压，由导纳核验电容分量。 |
| De-embedding | 去嵌／去嵌入 | 依据已验证的夹具等效网络移除焊盘、引线和开关等寄生。 |
| Length Differencing | 长度差分 | 使用端部等效且同相位的不同长度结构提取每节距增量参数。 |
| Direct Bit Transistor Access，DBTA | 直接位单元晶体管访问法 |  |
| Pulsed Measurement | 脉冲测量 |  |
| DC Clamping | 直流钳位 |  |
| Floating-Bitline Method | 浮置位线法／浮置位线电压反推 | 依据已标定电容和位线电压变化反推净电流，单元贡献须另扣外围静态漏电。 |
| Static Leakage Calibration | 静态漏电校准 | 在相同端口与偏置下测量静态漏电基线，明确扣除范围。 |
| Phase Sweep | 相位扫描 |  |
| Waveform Reconstruction | 波形重建 |  |
| Pulse-Width Replication | 脉宽复制法 | 取得脉宽代理量，不能单独提取同一边沿的两个幅度交点。 |
| Binary Search／Bisection Search | 二分搜索／二分法 | 须先验证所扫量与判决的单调性及单一分界。 |
| Driven Guard／Guarding | 驱动保护／守卫 |  |
| Current Compliance | 限流 |  |
| Thermoelectric Voltage | 热电势 |  |
| Measurement Uncertainty | 测量不确定度 |  |
| Detection Limit | 检测限 |  |
| Limit of Quantification，LOQ | 定量限 |  |
| Marginal Current | 边际电流 | 复制数量与总电流拟合的斜率。须保持每路偏置和负载不变。 |

## 统计分布、抽样与评估

| 英文／缩写 | 中文 | 必要说明 |
| --- | --- | --- |
| Central Limit Theorem，CLT | 中心极限定理 |  |
| Cumulative Distribution Function，CDF | 累积分布函数 | 经验估计对应 ECDF，须与总体分布函数区分。 |
| Empirical Cumulative Distribution Function，ECDF | 经验累积分布函数 |  |
| Exceedance Probability | 超限概率 |  |
| Normal Distribution／Gaussian Distribution | 正态分布 |  |
| Lognormal Distribution | 对数正态分布 |  |
| Multimodal Distribution | 多峰分布 |  |
| Bimodal Distribution | 双峰分布 |  |
| Generalized Extreme Value Distribution，GEV | 广义极值分布 |  |
| Gumbel Distribution | 耿贝尔分布 |  |
| Joint Distribution | 联合分布 |  |
| Conditional Distribution | 条件分布 | 仅用达标样本统计时须标明条件。 |
| Conditional Probability | 条件概率 |  |
| Covariance | 协方差 |  |
| Correlation Coefficient | 相关系数 |  |
| Spatial Correlation | 空间相关性 |  |
| Relative Standard Deviation／Coefficient of Variation | 相对标准差／变异系数 |  |
| Confidence Interval | 置信区间 |  |
| Binomial Confidence Interval | 二项置信区间 |  |
| Censoring | 删失／截尾 | 保留观测界限外的样本及其界限，须与已确认的功能失效分列。 |
| Left Censoring | 左删失 | 记录各样本的测量下限，按左删失保留样本计数。 |
| Right Censoring | 右删失／右截尾 | 因采集限长而未观测到目标事件，功能失效须另计。 |
| Monte Carlo Simulation，MC | 蒙特卡洛仿真 |  |
| Resampling | 重采样 |  |
| Subsampling | 子采样 |  |
| Importance Sampling | 重要性采样 |  |
| Mixture Importance Sampling | 混合重要性采样 |  |
| Gradient Importance Sampling | 梯度重要性抽样 |  |
| Gibbs Sampling | Gibbs 采样 |  |
| Subset Simulation | 子集模拟 |  |
| Recursive Statistical Blockade | 递归统计阻断 |  |
| Most Probable Failure Point，MPFP | 最可能失效点 |  |
| Effective Sample Size | 有效样本量 |  |
| Principal Component Method | 主成分方法 |  |
| Detrending | 去趋势 | 提取局部失配时去除系统性空间趋势。 |
| Logarithmic Transformation | 对数变换 |  |
| Linear Fit | 直线拟合 |  |
| Fit Residual | 拟合残差 |  |
| Linear Interpolation | 线性插值 |  |
| Deep Neural Network，DNN | 深度神经网络 |  |
| Wafer Map | 晶圆图 |  |
| Quantile–Quantile Plot，Q–Q Plot | 分位数–分位数图 |  |
| Shmoo Plot | 二维通过／失效图（Shmoo 图） | 以多参数扫描显示通过与失效分布。 |

## 使用约定

1. **端子标注**：源漏定义遵循器件符号、PDK／模型及适用状态，不按电源网名推断端子；双向器件仅描述拓扑时使用“源漏两端分别连接……”。
2. **原始标识**：文献原文、参考文献条目、器件型号、模型引脚、网表标识及原始数据字段保留原样，必要时说明对应术语。
3. **例外说明**：特殊工艺、拓扑、偏置、符号及测量边界，在使用处注明实际定义与适用条件。
