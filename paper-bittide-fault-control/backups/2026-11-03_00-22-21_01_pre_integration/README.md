# ACM 双栏会议论文模板

本项目使用 `\documentclass[sigconf]{acmart}`，保留 ACM 默认字号、页边距和双栏布局，以及 `ACM-Reference-Format` 参考文献格式。正文为可替换的英文论文框架，不包含真实研究结果。

## 在 VS Code 中编译

1. 用 VS Code 的“文件 → 打开文件夹”打开整个 `ACM-Conference-Paper` 文件夹。
2. 打开 `main.tex`，保存后 LaTeX Workshop 会自动编译。
3. 也可按 `Ctrl+Alt+B` 编译，按 `Ctrl+Alt+V` 预览 PDF。
4. 编译结果位于 `build/main.pdf`。

这台电脑已检测到 TeX Live 2025、`latexmk`、`acmart` 和 LaTeX Workshop。其他电脑需安装 TeX Live 或 MiKTeX，并确保 `latexmk`、pdfLaTeX、BibTeX 可以在终端运行。Windows 上使用 MiKTeX 时，latexmk 还需要 Perl。

在项目目录的终端也可以运行：

```powershell
latexmk -pdf -synctex=1 -interaction=nonstopmode -file-line-error -outdir=build main.tex
```

## 文件说明

- `main.tex`：标题、作者、摘要、CCS、关键词、正文、公式、图表和致谢。
- `references.bib`：参考文献；正文使用 `\cite{key}` 或 `\citet{key}`。
- `images/`：论文图片。
- `.vscode/`：自动编译、BibTeX 和 PDF 预览设置。
- `build/main.pdf`：本地编译生成的 PDF。

## 开始写作

替换标题、作者和机构信息，以及各节的占位内容。新增 BibTeX 条目后在正文引用，latexmk 会自动运行 BibTeX 并完成多轮编译。使用 `figure` 放单栏图，使用 `figure*` 放跨双栏图；不要手动修改 ACM 的版心或字体大小。

当前会议名、日期、地点均为明确的占位信息；DOI 和 ISBN 留空，版权设为 `none`，适合本地起稿。最终发表前须使用 ACM rights form 和会议方提供的正式版权、会议、DOI、ISBN 元数据。CCS 示例也应通过 https://dl.acm.org/ccs 替换。

当前按要求使用双栏。若会议要求匿名双栏，可将第一条命令改为 `\documentclass[sigconf,anonymous,review]{acmart}`，并移除致谢及其他身份信息；若会议要求单栏审稿，请遵循会议说明使用 `manuscript` 等选项。格式应以具体会议的投稿要求为准。

此框架默认用 pdfLaTeX 编译英文论文；中文正文需要另行配置中文字体与编译器。

ACM 官方模板入口：https://www.acm.org/publications/proceedings-template
