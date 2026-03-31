# 现代中文 PhD 论文模板

基于 ctex 宏包的现代化 LaTeX 中文论文模板，使用 XeLaTeX 编译。

## 编译说明

### 编译方式

使用 XeLaTeX 编译：

```bash
# 单次编译
xelatex thesis

# 完整编译（推荐）
xelatex thesis
bibtex thesis
xelatex thesis
xelatex thesis
n```

或使用 latexmk：

```bash
latexmk -xelatex thesis
```

### 编译依赖

必需宏包：
- ctex（核心中文支持）
- geometry（页面布局）
- amsmath, amssymb, amsfonts（数学）
- graphicx（插图）
- caption, subcaption（图表标题）
- hyperref（超链接）
- natbib（参考文献）
- fancyhdr（页眉页脚）
- booktabs, multirow, array（表格）
- setspace（行距）
- enumitem（列表）
- etoolbox（编程工具）
- datetime2（日期时间）
- tikz（绘图）
- mathrsfs（花体字体）
- xcolor（颜色）
- indentfirst（首行缩进）
- footmisc（脚注）

### 字体依赖

默认使用 Fandol 字体（包含在 TeX Live 中），无需额外安装。

如需使用系统字体，修改 `package.tex`：

```latex
% Windows 系统
\usepackage[UTF8,heading=true,zihao=-4,fontset=windows]{ctex}

% macOS 系统
\usepackage[UTF8,heading=true,zihao=-4,fontset=mac]{ctex}

% Linux/通用（Fandol 字体）
\usepackage[UTF8,heading=true,zihao=-4,fontset=fandol]{ctex}
```

## 文件结构

```
.
├── thesis.tex              # 主文件
├── setup/
│   ├── package.tex         # 宏包配置（新版）
│   └── format.tex          # 格式配置（新版）
├── chapter/
│   ├── Cover_C.tex         # 中文封面
│   ├── Cover_E.tex         # 英文封面
│   ├── originauth.tex      # 原创性声明
│   ├── Abstract_C.tex      # 中文摘要
│   ├── Abstract_E.tex      # 英文摘要
│   ├── Introduction.tex    # 引言
│   ├── Chapter_Two.tex     # 第二章
│   ├── Conclusion.tex      # 结论
│   ├── Appendix.tex        # 附录
│   ├── Publication.tex     # 发表论文
│   └── Thanks.tex          # 致谢
├── figures/                # 图片目录
│   └── hblogo              # 校徽
└── Ref.bib                 # 参考文献数据库
```

## 注意事项

1. **编译引擎**：必须使用 XeLaTeX，不支持 pdfLaTeX
2. **参考文献**：使用 `\bibliographystyle{JHEP}` 保持格式兼容
3. **章节引用**：保留"第X章"格式，自动处理
4. **页眉页脚**：与原模板保持一致

## 常见问题

### 1. 字体找不到

如果编译时提示字体缺失，可以：
- 安装 Fandol 字体包
- 或修改 `package.tex` 使用系统字体（fontset=windows/mac）

### 2. 参考文献格式

确保使用 JHEP.bst 文件，与原文档格式保持一致。

### 3. 图片格式

支持 PNG, JPG, PDF 格式图片，推荐使用 PDF 格式矢量图。

## 版本信息

- 模板版本：2.0（ctex 现代化版本）
- 更新日期：2025年3月
- 编译要求：TeX Live 2020+ 或 MiKTeX 21+
