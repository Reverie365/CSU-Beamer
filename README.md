# CSU Beamer

中南大学风格的轻量 XeLaTeX Beamer 模板。项目面向学术汇报、组会、论文答辩和课程展示，保留固定高度顶栏、章节导航、标题栏、页脚、衬线排版、三线表和定理环境，并使用中南大学校徽作为每页的淡色背景。

> 这是一个非官方的中南大学 Beamer 模板。

## 模板特点

- 默认使用 16:9 画幅，也支持切换为 4:3。
- 使用 `ctex` 和 XeLaTeX 支持中文排版。
- 使用 XCharter 衬线英文字体，并提供中文字体回退配置。
- 使用中南蓝作为主题色（`RGB 25, 98, 153`）。
- 标题页和正文标题栏右上角显示中南大学中英文校徽组合图。
- 每一页使用中南大学校徽淡色背景。
- 提供顶部章节导航、页脚页码、引用、块环境、定理环境和三线表样式。
- 支持 BibTeX，并附带一个可以直接修改的示例演示文稿。

## 示例预览

项目中的 [main.pdf](main.pdf) 是示例演示文稿的编译结果。修改 `main.tex` 中的标题、作者、单位和日期，即可开始制作自己的幻灯片。项目使用 XeLaTeX 编译，推荐使用 `latexmk -xelatex main.tex` 完成多轮编译和参考文献处理。

## 项目结构

```text
.
├── CSU.sty              # CSU 主题样式
├── main.tex             # 示例演示文稿和编译入口
├── main.pdf             # 示例 PDF
├── ref.bib              # BibTeX 示例数据库
├── figures/
│   ├── background.png   # 校徽淡色背景
│   ├── logo.png         # 中南大学中英文校徽组合图
│   └── fig1.png         # 示例图片
├── clean.sh             # 清理脚本
├── LICENSE
└── README.md
```

## 自定义方法

在 `main.tex` 中修改以下信息：

```tex
\title[短标题]{演示文稿标题}
\subtitle{可选副标题}
\author[简短作者名]{作者姓名}
\institute{中南大学某学院或单位}
\date{\today}
```

将演示文稿图片放入 `figures/`，并同步修改 `\includegraphics` 路径。主题默认使用 `figures/logo.png` 作为标题页和正文标题栏校徽，使用 `figures/background.png` 作为整页背景。

## 清理编译文件

```bash
./clean.sh          # 清理中间文件，保留 main.pdf
./clean.sh --deep   # 同时删除 main.pdf 和 main.bbl
```

Windows 用户可以在 Git Bash 中运行脚本，也可以使用等价命令 `latexmk -c main`。

## 致谢与参考项目

本项目的版式和实现参考了以下项目：

- [HexaMPA/CSU_Beamer](https://github.com/HexaMPA/CSU_Beamer)：早期的中南大学 Beamer 模板。
- [rexera/minimalist-pku-beamer-2026](https://github.com/rexera/minimalist-pku-beamer-2026)：本项目版式、字体和页面结构的重要参考来源。

本仓库是在上述项目基础上的独立中南大学适配版本，不代表中南大学官方发布。

## 协作者

- [Reverie365](https://github.com/Reverie365)：项目维护者。
- [OpenAI Codex](https://openai.com/codex/)：协助完成模板适配、资源整理、文档编写和编译验证。

## 许可证与校徽使用

主题源代码使用 [MIT License](LICENSE) 发布。中南大学校徽和校名图形属于中南大学视觉资产，使用时请遵守学校的相关规范。发布自己的幻灯片前，请替换示例中的作者、邮箱和单位信息。
