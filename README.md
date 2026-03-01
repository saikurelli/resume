# Sai Kurelli's Resume

This repository contains my resume written in LaTeX (`Sai's_Resume.tex`) and the compiled PDF (`Sai's_Resume.pdf`).

## Prerequisites: Installing pdflatex

### Linux (Ubuntu / Debian)

```bash
sudo apt-get update
sudo apt-get install -y texlive-latex-base texlive-fonts-recommended texlive-fonts-extra texlive-latex-extra
```

For a full TeX Live installation (includes all packages):

```bash
sudo apt-get install -y texlive-full
```

### macOS

Install [MacTeX](https://www.tug.org/mactex/) (includes pdflatex):

```bash
brew install --cask mactex
```

Or install the smaller BasicTeX distribution:

```bash
brew install --cask basictex
```

After installing BasicTeX, add any missing packages with `tlmgr`:

```bash
sudo tlmgr update --self
sudo tlmgr install collection-fontsrecommended fontawesome
```

### Windows

Download and install [MiKTeX](https://miktex.org/download) or [TeX Live for Windows](https://www.tug.org/texlive/windows.html). Both include pdflatex and will auto-install missing packages on first compile.

---

## Compiling the Resume

```bash
pdflatex "Sai's_Resume.tex"
```

Run twice to resolve cross-references and bookmarks:

```bash
pdflatex "Sai's_Resume.tex"
pdflatex "Sai's_Resume.tex"
```

The compiled PDF will be output as `Sai's_Resume.pdf`.

## Verifying the Output is 1 Page

After compiling, verify the PDF is exactly 1 page. The pdflatex output line will show:

```
Output written on Sai's_Resume.pdf (1 page, XXXXX bytes).
```

To check programmatically:

```bash
pdflatex "Sai's_Resume.tex" 2>&1 | grep "Output written"
# Expected: Output written on Sai's_Resume.pdf (1 page, ...)
```

**Important:** The resume must always be exactly 1 page. If it overflows to 2+ pages, adjust spacing or content in the `.tex` file before committing.
