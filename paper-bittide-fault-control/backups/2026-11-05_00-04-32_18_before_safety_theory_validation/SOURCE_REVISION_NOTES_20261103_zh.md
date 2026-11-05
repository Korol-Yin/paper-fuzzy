# 2026-11-03：仅源文件扩写

当前活动主稿仍为 `main.tex`，ACM `acmart/sigconf` 和标题/作者信息保留。

- Section II `sections/background.tex`：已先在规划对话展示英文正文，随后导入。涵盖 logical synchrony、连续相位与接收buffer、轨迹安全/频差/居中、delivery perturbation 和公开控制基础；四个既有公开文献键均保留。
- Section III `sections/section_iii_paper.tex`：改为长版，不按页数压缩；补齐完整控制器、连续模型、计数/送达、单位、PI校准和初始化、分象限曲面、sector和非线性记忆。
- Section IV `sections/section_iv_paper.tex`：改为长版；完整说明参考假设、ZOH端点、bootstrap、投影、Lyapunov证书、不变域、buffer安全、频率差阈值、正频率/限幅和全时间比较。
- 新增阈值推论只适用于声明的同步、零延迟fluid参考。它不证明实际异步/变化延迟Callisto，更不证明Fuzzy在所有指标上优于PI。
- 主稿摘要仍为待写状态；Evaluation、Discussion、Conclusion仍待完成。

## 保留的中间版

- 扩写前完整源文件备份：`C:\Users\cyin969\Documents\paper-fuzzy\paper-bittide-fault-control\backups\2026-11-03_02-06-43_02_pre_expansion`
- 第三/第四部分导入后的TeX快照：`C:\Users\cyin969\Documents\paper-fuzzy\paper-bittide-fault-control\backups\2026-11-03_02-12-12_03_after_expanded_iii_iv`
- 第二至第四部分导入后的TeX快照：`C:\Users\cyin969\Documents\paper-fuzzy\paper-bittide-fault-control\backups\2026-11-03_02-15-29_04_after_background_ii_iii_iv`

## 仅源文件工作与检查

本任务未调用 latexmk、pdflatex、BibTeX、PDF渲染或simulation；只进行了源文件静态检查及既有证书的纯数学check-only复核。TeX源检查记录见 `source_checks_20261103.json`。不把源文件检查表述为新稿的编译或排版验收。

已将项目 `.vscode/settings.json` 及父目录 `C:\Users\cyin969\Documents\paper-fuzzy\.vscode\settings.json` 的 `latex-workshop.latex.autoBuild.run` 设为 `never`。仍保留手动编译recipe。

修改TeX期间观察到外部编译更新了既有main.pdf/main.log；本任务没有发起该编译，检查时没有活动TeX进程，确切外部触发来源未确定。此事件已如实记录在 `source_revision_20261103.json`，不把该PDF作为本任务新交付物，也未为其执行渲染/排版检查。后续以当前TeX源文件为准。

第二部分经独立范围复核：精确nominal收敛目标明确标为fluid目标。此最终小修订前版本保留，最新源文件快照：`C:\Users\cyin969\Documents\paper-fuzzy\paper-bittide-fault-control\backups\2026-11-03_02-20-58_05_after_background_scope_review`。

第五部分后续已写入，见 `EVALUATION_SOURCE_NOTES_20261103_zh.md`；旧记录的Evaluation待写状态对应之前版本。
