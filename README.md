# 华中师范大学理学学位论文 LaTeX 模板

## 简介

本仓库包含华中师范大学理学硕士和理学博士学位论文的 LaTeX 模板，基于现代 `ctex` 宏包，使用 XeLaTeX 编译。

## 模板特点

- ✅ 使用现代 `ctex` 宏包（替代旧版 xeCJK）
- ✅ 支持 XeLaTeX 编译
- ✅ 自动处理中文字体和排版
- ✅ 符合华中师范大学学位论文格式要求
- ✅ 支持目录、图表、参考文献
- ✅ 兼容 JHEP 参考文献格式

## 文件结构

```
Thesis_Template/
├── README.md                 # 本说明文档
├── Ms_template/              # 硕士论文模板
│   ├── README.md            # 硕士模板说明
│   ├── main.tex             # 主文件
│   ├── Refs.bib             # 参考文献数据库
│   ├── JHEP.bst             # JHEP 参考文献样式
│   ├── setup/
│   │   ├── package.tex      # 宏包配置
│   │   └── format.tex       # 格式配置
│   ├── chapter/             # 章节文件
│   │   ├── A_Title_C.tex    # 中文封面
│   │   ├── A_Title_E.tex    # 英文封面
│   │   ├── B_originauth.tex # 原创性声明
│   │   ├── C_Abstract_C.tex # 中文摘要
│   │   ├── C_Abstract_E.tex # 英文摘要
│   │   ├── D_introduction.tex    # 引言
│   │   ├── E_chapter_two.tex     # 第二章
│   │   ├── F_chapter_three.tex   # 第三章
│   │   ├── G_chapter_four.tex    # 第四章
│   │   ├── H_conclusions.tex     # 结论
│   │   ├── I_appendixa.tex       # 附录A
│   │   ├── J_appendixb.tex       # 附录B
│   │   ├── O_papers.tex          # 发表论文
│   │   └── P_thanks.tex          # 致谢
│   └── figures/             # 图片目录
│
└── PhD_template/             # 博士论文模板
    ├── README.md            # 博士模板说明
    ├── thesis.tex           # 主文件
    ├── Ref.bib              # 参考文献数据库
    ├── JHEP.bst             # JHEP 参考文献样式
    ├── jheppub.sty          # JHEP 出版样式
    ├── setup/
    │   ├── package.tex      # 宏包配置
    │   └── format.tex       # 格式配置
    ├── chapter/             # 章节文件
    │   ├── Cover_C.tex      # 中文封面
    │   ├── Cover_E.tex      # 英文封面
    │   ├── Originauth.tex   # 原创性声明
    │   ├── Abstract_C.tex   # 中文摘要
    │   ├── Abstract_E.tex   # 英文摘要
    │   ├── Introduction.tex # 引言
    │   ├── Chapter_Two.tex  # 第二章
    │   ├── Conclusion.tex   # 结论
    │   ├── Appendix_A.tex   # 附录A
    │   ├── Appendix_B.tex   # 附录B
    │   ├── Publication.tex  # 发表论文
    │   └── Thanks.tex       # 致谢
    └── figures/             # 图片目录
```

## 编译说明

### 环境要求

- TeX Live 2020 或更高版本
- XeLaTeX 编译引擎
- 支持中文的字体（Fandol 或系统自带中文字体）

### 编译方式

#### 方式一：手动编译

```bash
# 进入硕士模板目录
cd Ms_template
xelatex main.tex
bibtex main
xelatex main.tex
xelatex main.tex

# 或进入博士模板目录
cd PhD_template
xelatex thesis.tex
bibtex thesis
xelatex thesis.tex
xelatex thesis.tex
```

#### 方式二：使用 latexmk 自动编译

```bash
# 硕士模板
cd Ms_template
latexmk -xelatex main.tex

# 博士模板
cd PhD_template
latexmk -xelatex thesis.tex
```

### 编译步骤说明

1. **第一次编译**：生成辅助文件（.aux, .toc）
2. **第二次编译**：读取辅助文件，生成目录
3. **第三次编译**：确保交叉引用正确

## 使用指南

### 1. 选择模板

- **硕士论文**：使用 `Ms_template/`
- **博士论文**：使用 `PhD_template/`

### 2. 填写封面信息

编辑封面文件（如 `chapter/A_Title_C.tex`）：

```latex
% 中文封面
论文作者: 你的名字
指导教师: 导师姓名 教授
专业名称: 你的专业
研究方向: 你的方向
```

### 3. 编写摘要

编辑摘要文件（如 `chapter/C_Abstract_C.tex`）：

```latex
% 中文摘要
本文研究了...

{\heiti \bfseries{关键词：}}关键词1；关键词2；关键词3
```

### 4. 编写正文

在各章节文件中编写内容，如 `chapter/E_chapter_two.tex`。

### 5. 添加参考文献

在 `Refs.bib` 或 `Ref.bib` 中添加 BibTeX 格式的参考文献条目。

### 6. 添加图片

将图片放入 `figures/` 目录，使用：

```latex
\includegraphics[width=0.8\textwidth]{figures/picture.png}
```

## 常见问题

### Q1: 编译报错 "Missing \\begin{document}"

**A:** 确保主文件中有 `\begin{document}` 命令。

### Q2: 目录不显示

**A:** 需要编译三次才能生成完整的目录。

### Q3: 中文字体显示不正常

**A:** 确保使用 XeLaTeX 编译，不是 pdfLaTeX。

### Q4: 如何修改页边距

**A:** 编辑 `setup/format.tex` 中的 `geometry` 设置。

### Q5: 目录页有页码

**A:** 模板已修复，目录页使用 `\thispagestyle{empty}` 不显示页码。

### Q6: 硕士和博士模板有什么区别

**A:** 主要区别在封面字样（硕士/博士），其他格式基本一致。

## 技术细节

### 使用的宏包

- **ctex**: 中文排版核心宏包
- **geometry**: 页面布局
- **fancyhdr**: 页眉页脚
- **caption/subcaption**: 图表标题
- **hyperref**: 超链接和 PDF 书签
- **cleveref**: 智能交叉引用
- **natbib**: 参考文献

### 中文字体

- 正文字体：Fandol 字体（跨平台兼容）
- 标题字体：黑体
- 正文字体：宋体

### 页面设置

- 纸张：A4
- 页边距：上下 3.9cm/3.5cm，左右 2.9cm
- 页眉：15mm（含 Logo）
- 页脚：8mm

## 许可证

本模板仅供学习和研究使用，遵循MIT开源协议。

---

**注意**: 本模板由用户维护，非官方模板。使用前请确认符合学校最新要求。
