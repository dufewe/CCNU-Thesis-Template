# 华中师范大学硕士论文 LaTeX 模板

## 简介

本模板是基于 `ctex` 宏包的现代化 LaTeX 中文论文模板，使用 XeLaTeX 编译，兼容 JHEP 参考文献格式。

## 特点

- 使用现代 `ctex` 宏包
- 支持 XeLaTeX 编译
- 自动处理中文字体和排版
- 支持目录、图表、参考文献
- 符合华中师范大学硕士论文格式要求

## 文件结构

```
Ms_template/
├── main.tex              # 主文件
├── README.md             # 本文件
├── Refs.bib        # 参考文献数据库
├── JHEP.bst              # JHEP 参考文献样式
├── setup/
│   ├── package.tex       # 宏包配置
│   └── format.tex        # 格式配置
├── chapter/
│   ├── A_Title_C.tex     # 中文封面
│   ├── A_Title_E.tex     # 英文封面
│   ├── B_originauth.tex  # 原创性声明
│   ├── C_Abstract_C.tex  # 中文摘要
│   ├── C_Abstract_E.tex  # 英文摘要
│   ├── D_introduction.tex    # 引言
│   ├── E_chapter_two.tex     # 第二章
│   ├── F_chapter_three.tex   # 第三章
│   ├── G_chapter_four.tex    # 第四章
│   ├── H_conclusions.tex     # 结论
│   ├── I_appendixa.tex       # 附录A
│   ├── J_appendixb.tex       # 附录B
│   ├── O_papers.tex          # 发表论文
│   └── P_thanks.tex          # 致谢
└── figures/              # 图片目录
```

## 编译说明

### 编译方式

使用 XeLaTeX 编译：

```bash
xelatex main.tex
xelatex main.tex
xelatex main.tex
```

或使用 `latexmk`：

```bash
latexmk -xelatex main.tex
```

### 编译步骤

1. 第一次编译：生成辅助文件（.aux, .toc）
2. 第二次编译：读取辅助文件，生成目录
3. 第三次编译：确保交叉引用正确

## 使用指南

### 1. 填写封面信息

编辑 `chapter/A_Title_C.tex` 和 `chapter/A_Title_E.tex`：

```latex
% 中文封面
论文作者: 你的名字
指导教师: 导师姓名 教授
专业名称: 你的专业
研究方向: 你的方向

% 英文封面
by Your Name
Supervisor: Prof. Advisor Name
Specialty: Your Specialty
Research Area: Your Research Area
```

### 2. 填写摘要

编辑 `chapter/C_Abstract_C.tex` 和 `chapter/C_Abstract_E.tex`：

```latex
% 中文摘要
本文研究了...

{\heiti \bfseries{关键词：}}关键词1；关键词2；关键词3

% 英文摘要
This thesis studies...

{\bfseries Key Words: }keyword1; keyword2; keyword3
```

### 3. 编写正文

在 `chapter/D_introduction.tex` 等文件中编写各章节内容。

### 4. 添加参考文献

在 `References.bib` 中添加 BibTeX 格式的参考文献条目。

### 5. 添加图片

将图片放入 `figures/` 目录，使用：

```latex
\includegraphics[width=0.8\textwidth]{figures/picture.png}
```

## 常见问题

### Q1: 编译报错 "Missing \\begin{document}"

**A:** 确保 `main.tex` 中有 `\begin{document}` 命令。

### Q2: 目录不显示

**A:** 需要编译三次才能生成完整的目录。

### Q3: 中文字体显示不正常

**A:** 确保使用 XeLaTeX 编译，不是 pdfLaTeX。

### Q4: 如何修改页边距

**A:** 编辑 `setup/format.tex` 中的 `geometry` 设置。

## 许可证

本模板仅供学习和研究使用。
