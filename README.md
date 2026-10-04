# Academic CV & One-Page Résumé — LaTeX Template

A matched pair of clean, classical LaTeX templates:

| File | What it is |
|---|---|
| [`cv.tex`](cv.tex) | Full academic **Curriculum Vitae**: multi-page, with a running header and "page X of Y" footer |
| [`resume.tex`](resume.tex) | **One-page résumé** for industry and ATS systems |
| [`cvstyle.sty`](cvstyle.sty) | Shared style both documents load, so they always match |
| [`examples/`](examples) | PDFs compiled from the templates as they ship |

## Features

- **One shared style file.** Fonts, headings, entries and lists are defined once in `cvstyle.sty`
- **Standard section names and order.** These follow common US résumé and academic CV practice
- **ATS-friendly.** Single column, no tables or graphics, and text that copies out as plain words
- **Consistent entry format** in both documents:
  ```
  Organization                                   Location
  Role or degree                                    Dates
  ```
- Publications in **APA style**, auto-numbered **[J1]**, **[C1]**, **[P1]**
- Libertinus Serif with true small caps (falls back to Liberation Serif or Times New Roman)
- The CV has a running header with your name and "page X of Y" on every page

## Standard conventions

| | Résumé | CV |
|---|---|---|
| **Length** | 1 page | As long as needed |
| **Section order** | Summary, Experience, Education, Skills, Projects, Publications, Certifications, Awards | Research Interests, Education, Appointments, Publications, Grants, Awards, Research, Teaching, Mentoring, Talks, Service, Certifications, Memberships, References |
| **Position dates** | `Aug 2024 -- Present` | `Aug 2024 -- Present` |
| **Degree dates** | Conferral date only: `May 2024` or `Expected May 2026` | Same |
| **Locations** | `City, ST` or `City, Country` | Same |
| **Citations** | APA, your name in bold | APA, reverse chronological, numbered |
| **Paper** | US Letter (switch to `a4paper` in `\documentclass` elsewhere) | Same |

## Quick start

### Option 1: Overleaf (no install)
1. Download this repo as a ZIP and upload it to [Overleaf](https://www.overleaf.com) as a new project. Keep `cvstyle.sty` in the same folder as the `.tex` files.
2. Go to **Menu → Compiler** and choose **XeLaTeX**.
3. Edit and recompile.

### Option 2: Local
Requires a TeX distribution ([TeX Live](https://tug.org/texlive/), [MacTeX](https://tug.org/mactex/), or [MiKTeX](https://miktex.org/)).

```bash
xelatex cv.tex && xelatex cv.tex   # run twice so "page X of Y" resolves
xelatex resume.tex
```

## Customizing

1. Set your name near the top of each file:
   ```latex
   \newcommand{\myname}{Your Name}
   ```
2. Replace the placeholder header details (title, location, email, links, ORCID).
3. Fill in or delete sections. Each one is marked with a `%=== SECTION ===` banner.

### Commands (from `cvstyle.sty`)

| Command | Use |
|---|---|
| `\cvheader{Name}{Title}{Contact}` | Centered header. Separate contact items with `\cvsep` |
| `\entry{Organization}{Location}{Role or degree}{Dates}` | Two-line entry for jobs, degrees and positions. Follow it with `itemize` bullets |
| `\dated{Text}{Date}` | One line with the date right-aligned (awards, talks, service, certifications) |
| `\begin{publist}{J} ... \end{publist}` | Numbered publication list labeled [J1], [J2], ... (any prefix works) |
| `\me{Lastname, F.}` | Bolds your name in author lists |

### Changing the look
Edit `cvstyle.sty` and both documents update together.
- **Link color:** `\definecolor{cvlinkcolor}{RGB}{20,70,130}`
- **Font:** replace the `\setmainfont` block with any installed OpenType font
- **Margins:** the `\geometry{...}` line in each `.tex` file

## Tips
- Keep the résumé to **one page**. If it overflows, trim bullets before you shrink margins.
- Begin each bullet with a verb and include a number where you can.
- Keep one date format throughout. Mixing `2024`, `08/2024` and `August 2024` reads as careless.
- Leave out photos, date of birth and marital status. US and UK applications expect them to be omitted.

## License

[MIT](LICENSE). Use it, change it, and share it freely. No attribution is required.
