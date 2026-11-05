# 论文整合记录（20261103_002221，Pacific/Auckland）

## 来源与备份

目标：`C:/Users/cyin969/Documents/paper-fuzzy/paper-bittide-fault-control`。
整合源：`C:/Users/cyin969/Documents/Codex/2026-10-26/cps-weeks-4/output/pdf/Bittide_Controller_Sections_20261102_v3`。
写入目标项目前，将原稿完整保存为 `backups/pre_integration_20261103_002221/`。
准备阶段完整原稿快照：`C:/Users/cyin969/Documents/Codex/2026-10-29/new-chat/work/paper_fuzzy_integration/original_snapshot`。

## 手写内容处理

- 完整保留标题 `Fuzzy PI Control for bittide: Nonlinear Analysis and Transient Performance` 和原作者、机构、邮件块。仅增加页眉短标题。
- 作者的未完成引言开头 `The bittide is a ` 原样保存在 `author_notes/introduction_original.tex`，原始 `main.tex` 也在完整备份内。
- 主稿采用已确认的 Introduction v5 候选，并记录这一选择；没有将未完成的一句静默改写成研究论断。
- 原有通用 ML 方程、示例图表和 Lamport 示例引用不再进入活动正文，但均在备份中。

## 主稿内容与适配

- 保留 ACM 默认 sigconf 双栏、字号、页边距和章节编号（1--7，依次对应请求的 I--VII）。
- 第一、三、四部分分别用 input 引入；第二、五、六、七部分明确标为待写。摘要、致谢和出版元数据仍待最终确认。
- 引言的 Markdown 链接改为 BibTeX 引用，贡献列表改为 enumerate；公开条目已合并，内部未发表 report 不虚构为公开文献。
- 公开的 fluid occupancy 与 reframing 文献从原引言链接核实元数据后加入；没有为先前作者 study 编造作者/会议信息。
- 第三、四部分只做 ACM 兼容与排版调整：复用 acmart 的数学/定理宏包，使用独立 btd 定理名，将跨节文字改为 label/ref；长公式按双栏折行，完整数字区间表按 quantity 分行，保持单栏可读且所有区间端点原值不变。
- 保持来源中的控制律、所有常数、初态、证书与比较结论，不将详细推导整篇并入正文。

## 科研范围保持

- 本论文正式提出用于 bittide 的 Fuzzy PI；作者 report 未发表，不据此声称已有公开方法。
- Callisto 是连续物理时间/连续相位 plant；本地采样和整数帧是其中的事件，非 firing-count 离散 plant。
- 第四部分仅为同步、零延迟、fluid、ZOH 连续参考 flow 的精确端点证明。
- 17.315 与 23.403701... 的比较仅对指定三节点初态和匹配增益；不外推为延迟异步 Callisto 认证或全面优越性。
- 保留 buffer 安全、正频率、频率差界与收敛论证；不新加数值结论。
- Introduction 中保留原 v5 已确认的实验利弊；Evaluation 仍待移入完整方法与证据。

## 输出约定

主输出为项目根目录 `main.pdf`，恢复的 VS Code 配置与 `.latexmkrc` 一致。
原 `build/` 中旧 PDF 保存到备份后移入历史位置，避免两个 PDF 混淆。
此次仅整合论文并进行编译与视觉检查，不安装/升级 TeX，不运行或恢复 simulation、training、selection 或 Docker 任务。


## 最终核验

- 已在原论文项目成功编译为 6 页。63 个标签，无缺失引用、重复标签或重复书目键；4 个公开书目条目均被使用。
- 第三、四部分的数值 token 与源包保持一致；标题、作者块和手写引言开头保存核验通过。
- 无编译错误和栏宽溢出；有一处 Underfull vbox 间距提示，已逐页核查，没有文字/公式遮挡或孤立表格页。
- 原项目输出重新渲染后，6 页与已逐页审阅的整合稿像素一致。
- 最后页使用 acmart 已加载的 balance 机制；扩充待写章节后需重查该命令位置。
- 活动 build/main.pdf 已移入备份的 archived_from_active_build_main.pdf；当前输出唯一约定为项目根目录 main.pdf。
- 只做整合、编译、引用和排版核验；未新认证数学证明，也未运行任何仿真或训练。


## 后续源文件扩写（2026-11-03）

当前第二至第四部分已扩写；请以 `SOURCE_REVISION_NOTES_20261103_zh.md` 为准。旧版编译页数及视觉验收记录仅对应当时版本。本轮未主动编译，自动编译设置已关闭。

第五部分也已按现有证据整合（仅TeX），见 `EVALUATION_SOURCE_NOTES_20261103_zh.md`。
