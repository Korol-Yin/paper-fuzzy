# 学术术语一致性审查（2026-11-04）

已对当前 ACM 10 页正文及全部附录直接进行术语修订。原则是：相同概念优先沿用作者既有论文／报告的用词；作者未覆盖的概念采用 bittide 原论文或控制理论中更明确的术语；含义不同的量不为统一表述而混用。

## 对照来源

1. 作者最新本地稿：`Documents/MEMOCODE-Bittide-PI/Stabilizing the bittide.pdf`，14 页。重点对照第 2–4 页的物理模型、控制目标和控制输入定义；更早的 Final_ver 13 页稿也作交叉核查。
2. PYR 完整报告：`PYR_Finished/PYR draft/Thesis_Proposal_Full_Length_Korol__Final_PR.pdf`，54 页，题为 *Fault Tolerance and Control for Synchronized Distributed Systems*。重点对照第 5.2 节，PDF 第 20–23 页的 Fuzzy PI 定义、推理与输出。名为 `PYR Report.docx` 的本地文件只有少量占位文字，因此使用已有实质技术内容的 Final_PR 版本。
3. bittide 原始文献：*Logical Synchrony and the bittide Mechanism*、*Resistance Distance and Control Performance for bittide Synchronization*、*On Buffer Centering for Bittide Synchronization*、*Modeling Buffer Occupancy in bittide Systems*。

来源路径、页数、SHA256 和抽取文本保存在本次工作目录；项目中的 provenance JSON 给出索引。

## 主要术语决定

| 概念／原有表述 | 当前采用的用词 | 依据与准确性说明 |
|---|---|---|
| intrinsic frequency | uncontrolled oscillator frequency；首次并列 uncorrected | 作者旧稿采用 uncontrolled frequency；bittide PI 文献采用 uncorrected frequency。符号仍为 ωᵘ，不与运行基准频率或共同极限频率混同。 |
| oscillator correction／signed correction | frequency correction；applied control input | 与 PYR 的 frequency correction、control input 一致。继续区分 requested q 与 applied u。 |
| frequency correction increment | frequency correction increment | 沿用 PYR §5.2.4；不把增量误写为总频率或总修正。 |
| path delay／path latency | physical link latency；后文简称 link latency | 沿用旧稿核心术语。control-execution delay 单独保留，避免与链路传播混同。 |
| zero-delay fluid reference | zero-latency fluid reference | 更接近旧稿 zero-latency ideal model 的用词；参考模型处同时明确控制执行延迟也为零。 |
| frequency synchronization | frequency synchronization (syntony)，用于名义目标 | 沿用旧稿及 PYR。随机扰动下仍报告 disagreement，不把有限 RMS 当精确 syntony 证明。 |
| buffer occupancy／elastic buffers | buffer occupancy；elastic receiving buffers | 与作者及原论文一致。β 为 frame 数，百分比误差由 γ 转换。 |
| nominal centering | 分开说明 syntony 与 buffer centering | 防止读者把 frequency centering 理解成所有频率回到 1。主性能场景采用半容量目标；一般公式要求目标与初始化兼容。 |
| token-domain | frame-count／frame-error | bittide 原文和作者正文主要使用 frame。当前连续相位模型不改成 Petri-net token/firing-count plant。 |
| native PI | PI baseline／implemented PI baseline | “native”是实现标签，不是另一类控制器。保留先积分再输出的精确定义；原始图中的 Native PI 标签仍指相同基线，图形数据不重绘。 |
| untouched tests／profiles | held-out tests／profiles | 用标准验证术语表达测试数据未参与选参；未改变任何数据隔离或独立性主张。 |
| fuzzy memberships | fuzzification／membership functions | 沿用 PYR 的章节和技术用词。 |
| minimum inference | Mamdani minimum rule activation | 只说明 antecedent 的 min 运算，不声称采用完整 Mamdani 连续输出质心方法。 |
| output calculation | singleton weighted-average defuzzification | 与 PYR 的 singletons 和实际公式一致；保留逐规则求和，不能换成同后件 max aggregation。 |
| headroom | buffer headroom，明确定义为上下边界前的剩余 reserve | 旧稿的 safe domain 是增益域；不能将其当作 headroom 或一般鲁棒安全集的同义词。 |
| frequency disagreement RMS | 保留专门定义的 RMS 指标 | 不换成 temporal jitter、variance 或 absolute-frequency error，因为这些是不同指标。 |
| marking λ | 保留 marking／additive initialization offset 的精确定义 | 不直接改称 physical latency；UGN 偏移、初始在途帧与相对计数 marking 的区别保留。 |
| regional certificate／observed-safe | 保留 certificate 与 finite-time observation 的区别 | 不因报告使用 stable、meta stable、unsafe 就把“证书未满足”改写成系统不稳定。 |
| linear counterpart | 仅 F₀ 是线性对应面，完整 Fuzzy law 是非线性 | 不将标定关系称为完整 Fuzzy 控制器的线性化或线性控制器。 |
| spelling | neighbors、centers、modeling 等 American spelling | 与作者既有稿件的主要用法一致；专业概念与符号不变。 |

## 不直接照搬旧报告的地方

- 保留 E 为 frame-sum error、e 为百分点误差、X/Y 为 Fuzzy 输入，避免旧报告中 E 的不同用途冲突。
- 保留 u/q 的执行前后区别，不为接近旧稿而统一改成 c 并掩盖限幅。
- 保留 L 为 Laplacian、τ 为 physical link latency，避免旧稿 Q/L 与当前公式冲突。
- Fuzzy 输入的第二项是 sample difference，不直接称为时间导数；未引入在线调 Kp/Ki 或在线学习。
- PI 增益、采样尺度 h 与物理周期 H 的关系不变；本轮无控制器或仿真修改。

## 验证

逐文件检查显示：所有现有数学片段的多重集合、数值 token、公式标签及图像字节均保持不变。背景定义中调整了公式出现顺序，但未改公式内容。历史注释继续保留。

完成本地 pdfTeX draft-mode 与 BibTeX 检查：正文仍为 10 页，References 第 11 页，Appendix 第 12 页起，共 30 页；无未解析引用，无 overfull box。现有 PDF 被阅读器占用，普通 PDF 编译无法覆盖它，因此本轮以保存的 TeX 和独立 draft-mode 检查记录为准；不把旧 PDF 冒称为本轮最终排版。
