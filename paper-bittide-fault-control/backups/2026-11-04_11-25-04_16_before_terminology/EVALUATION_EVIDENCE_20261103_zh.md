# 第五部分与前文的证据闭合审查

日期：2026-11-03。范围是已完成结果的只读核查、论文写作及补充已有频率数据的描述性 max−min 计算；未启动仿真、未恢复暂停训练/选参、未生成新测试或PDF。

## 判断

现有结果足够写成完整 Evaluation，支撑当前标题下的“方法提出—非线性机制—条件性参考保证—实际性能权衡”。它们不能闭合“Fuzzy PI 普遍优于 PI，特别是在随机延迟和恢复速度上更好”的结论。现有 Introduction 已按有条件结论和权衡表述，基本与证据一致。

| 前文或预期观点 | 现有证据 | 可以写到什么程度 |
|---|---|---|
| 本文提出的 Fuzzy 控制器及其连续 Callisto 实现自洽 | 完整控制律；M0六对/12 actual，19,800 paired updates，最大命令差5.29e-18 | 支撑实现尺度、更新顺序与初始化；M0测试的是F0，不是full Fuzzy胜过PI |
| Fuzzy中央曲面能按输入符号关系塑造增量 | Section III代数、M2完整规则重放与残差恒等式 | 支撑具体机制；不能直接推出更小的实际闭环峰值或抖动 |
| buffer安全、正频率、频率差有界并收敛 | Section IV同步、零延迟fluid证书及原25规则reference检查 | 有明确条件的数学保证；actual有限安全运行是另外一类证据 |
| 特定初态下Fuzzy有更大buffer余量 | reference全时间Fuzzy<17.315 vs PI达到23.403701帧，差>6.088701帧 | 严格条件性优势；不是实际Callisto通用safe set扩大或硬件buffer减配结论 |
| 实际Callisto中Fuzzy能降低某些瞬态资源开销 | M2全窗口含startup偏移21 vs24帧；post-burst IAE降低1.864%、TV降低15.938% | 是当前可强调的实际有利端点，须固定窗口、控制器、配置和单例范围 |
| post-centering burst峰值更小、settling更快 | M2 post-window偏移21 vs20；RMS略高；component恢复时间相同 | 不支持。两者严格own-clean恢复均censored，不能写成已恢复或永久不恢复 |
| bounded random latency下Fuzzy更稳、活动更少 | M3两regime各30paired seeds；RMS比值1.19245和1.06791，均30/30更差；TV也更高 | 当前冻结对照反驳该范围内的优势假设。更好于stronger fixed PI不能覆盖moderate PI负结果 |
| actual频差满足IV的指定安全阈值 | M2补充max−min峰值69.1483/70.8916 ppm；未预设工程阈值 | 只有有限窗口描述；原σ-RMS不是Δ=max−min，更不能用window RMS冒充阈值证明 |
| actual安全/亚安全/失败分区验证了理论边界 | M2余量约1000帧、M3扰动窗最小余量1017帧 | 当前campaign远离边界，未建立该三档验证，也未验证证书的必要性 |
| 公平调参后仍值得采用Fuzzy | 冻结同预算campaign仍缺完结审计、selection与untouched tests | 只能说固定gain坐标的受控比较，不可声称优于独立调优PI或已有最佳控制器 |
| 始终logical synchrony且提高应用吞吐 | observed buffer safety、正频率、无guard干预及logical phase progress | 支撑有限模型正常执行；没有payload正确性、formal refinement或useful-throughput证明 |

## 最容易误写的模型与指标

1. 第四部分例子在Omega1内闭合不变域；M2 measured max(|X|+|Y|)=2.001888。M2仍在Omega5，故III的精确曲面公式成立，但不能套IV的Omega1证书。输入超出Omega1本身不意味着实际sector比值越界或失稳；异步、有delay、量化也已构成模型差别。
2. reference marking1024与actual delayed marking1044不可互换。C=2048的当前余量很大，更小偏移不等于分配buffer容量减少同样百分比。
3. s(t)是相对瞬时均值的跨节点RMS幅值；R_W是其时间RMS，IAE是其幅值积分；Delta是max−min。ppm以固定归一化频率1为基准，不是omega_base。
4. M2全窗口24/21与post-onset20/21分别保留；M3七帧峰值/1017余量只针对扰动窗口。不能挑窗口改变结论。
5. M2首次峰值早于首次变更指令，且相对同时间own-clean都缺20帧；21vs20的初次差别含nominal一帧偏置。不可全部归因于Fuzzy反馈更好或更差。
6. strict recovery比较window-mean common frequency与own-clean。相同component恢复时间不代表回到原频率；common稳定、节点相对同步和回到reference1是不同目标。

## 第五部分组织

1. Evidence groups and comparison design：M0、reference计算、M2、M3分别计数。
2. Continuous Callisto setup and delivery disturbances：参数表、固定burst、有界随机递推和共享trace。
3. Metrics, windows and finite-run admissibility：RMS/IAE/Delta/TV/buffer余量、事件完整重放、centering/recovery窗口标准。
4. Implementation equivalence and reference consistency：实现核验及原25规则的reference数值核对，区别于定理。
5. Response to a post-centering latency burst：明确有利端点、代价、窗口和恢复。
6. Observed nonlinear mechanism and the first buffer peak：精确曲面、记忆、因果时序。
7. Independent paired random-latency validation：30paired seeds、预存CI、两个PI参照、全部负结果。
8. What the completed evaluation establishes：对齐贡献并限定外推。

## 若要进一步闭合“值得采用”

优先完成已冻结的同预算训练与完整QA，固定selection后再使用未看过的新种子和held-out burst。此审查不恢复该工作，也不将已看过的M3 seeds变成新测试。

若要主张理论安全边界与actual表现的关系，需要另外设计：保持控制律、归一化、容量、拓扑和时间参数不变，以初态能量/频差等可控因素形成“证书内安全、证书外但实际安全、观察到约束违反”三档。证书外不等于必然失败；保护停顿也不能与无阻塞成功混为一谈。若改容量，需同步处理gamma与controller map变化。

若要主张burst/随机扰动的更广泛优势，预先固定幅值、持续时间、随机profile尺度和主指标，公平比较并保留所有不利结果；不能以筛出Fuzzy胜出的情形作为独立验证。

当前稿可以写“Fuzzy提供可分析的方向相关非线性响应与特定余量优势，但实际收益依赖端点和工况”。当前证据不适合写“Fuzzy已普遍解决PI的抖动/恢复问题”。
