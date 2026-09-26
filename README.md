# CSU Beamer

中南大学风格的轻量 XeLaTeX Beamer 模板。项目以简洁的学术演示为目标，保留固定高度顶栏、章节导航、标题栏、页脚、衬线排版、三线表和定理环境，并使用中南大学校徽作为每页的淡色背景。

> This is an unofficial Central South University Beamer template. It is designed for academic presentations, group meetings, thesis defenses and course reports.

## Features

- 16:9 widescreen layout, with an optional 4:3 switch.
- Native Chinese typesetting through `ctex` and XeLaTeX.
- Serif Latin text with XCharter and automatic CJK font fallback.
- CSU blue visual theme (`RGB 25, 98, 153`).
- The CSU emblem lockup on the title page and in the upper-right corner of titled frames.
- A light CSU emblem background on every slide.
- Consistent top navigation, footer page numbers, citations, blocks, theorem environments and booktabs tables.
- BibTeX bibliography support and a small example presentation that can be edited directly.

## Preview

The included [main.pdf](main.pdf) is a compiled preview of the example deck. Replace the title, author, institute and date in `main.tex` to start your own presentation.

## Requirements

Install a TeX distribution with the following components:

- XeLaTeX
- `latexmk`
- `ctex`
- Beamer, PGF/TikZ, XCharter and the other standard packages used by `main.tex`

TeX Live is recommended. The template is intended to be compiled with XeLaTeX because it contains Chinese text and CJK font configuration.

## Quick Start

```bash
latexmk -xelatex main.tex
```

Open `main.pdf` after compilation. You can also compile directly with `xelatex`, but `latexmk` automatically runs the required bibliography and cross-reference passes.

To switch to a 4:3 canvas, change `aspectratio=169` to `aspectratio=43` in the document class declaration in `main.tex`.

## Project Structure

```text
.
├── CSU.sty              # CSU theme definitions
├── main.tex             # Example presentation and entry point
├── main.pdf             # Compiled example PDF
├── ref.bib              # BibTeX example database
├── figures/
│   ├── background.png   # Light CSU emblem slide background
│   ├── logo.png         # CSU Chinese-English logo lockup
│   └── fig1.png         # Example figure
├── clean.sh             # Cleanup script
├── LICENSE
└── README.md
```

## Customization

Edit these commands in `main.tex`:

```tex
\title[Short title]{Presentation title}
\subtitle{Optional subtitle}
\author[Short author]{Author name}
\institute{School or department, Central South University}
\date{\today}
```

Put presentation images in `figures/` and update the corresponding `\includegraphics` path. The theme uses `figures/logo.png` for the title page and titled frames, and `figures/background.png` as the full-slide background.

## Cleaning Build Files

```bash
./clean.sh          # Remove intermediate files and keep main.pdf
./clean.sh --deep   # Also remove main.pdf and main.bbl
```

On Windows, run the script from Git Bash or use the equivalent `latexmk -c main` command.

## Credits and References

The layout and implementation were adapted with reference to:

- [HexaMPA/CSU_Beamer](https://github.com/HexaMPA/CSU_Beamer), an earlier Central South University Beamer template.
- [rexera/minimalist-pku-beamer-2026](https://github.com/rexera/minimalist-pku-beamer-2026), the minimalist Beamer layout whose typography and page structure inspired this project.

This repository is an independent CSU adaptation. It does not represent an official release by Central South University.

## License and Branding

The theme source code is released under the [MIT License](LICENSE). The Central South University emblem and wordmark are university trademarks and remain subject to the university's applicable usage requirements. Please replace the example author and contact information before publishing your own slides.
