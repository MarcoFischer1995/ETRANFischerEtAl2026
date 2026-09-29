# Paper agent: cell-to-pack scaling of capacity and resistance in 3 field-aged EV battery packs

[![Paper](https://img.shields.io/badge/Paper-eTransportation%2030%2C%20100636-0b5394)](https://doi.org/10.1016/j.etran.2026.100636)

An AI-readable version of our [open-access article](https://doi.org/10.1016/j.etran.2026.100636), packaged as an agent skill with [Paper2Agent](https://github.com/jmiao24/Paper2Agent) ([Miao et al., *Nature* 2026](https://doi.org/10.1038/s41586-026-11044-y)). Ask it about the teardown workflow, the measurements, the uncertainty analysis, figures and tables. Answers can be traced back to a section, figure or table of the paper.

> M. Fischer, M.J. Brand, A. Schröder, A. Jossen,
> **Teardown-Based cell-to-pack scaling of capacity and resistance in field-aged EV battery packs**,
> *eTransportation* 30 (2026) 100636. https://doi.org/10.1016/j.etran.2026.100636
>
> © 2026 The Authors. Published by Elsevier B.V. Open access under the CC BY 4.0 license.

## What is inside

| Folder / file | Content |
| --- | --- |
| `etran-fischer-et-al-2026-paper/SKILL.md` | Entry point for the agent |
| `.../references/paper.md` | Full article text, including equations as searchable transcriptions |
| `.../references/index.md` | Section navigation |
| `.../assets/figure/` | Figures 1 to 6, A.7 and B.8, equation images |
| `.../assets/table/` | Tables 1 to 6, C.7 and D.8 as CSV |

The package contains only the published article. It contains no raw data and no code. As stated in the article, data are available on request.

## Install

**Claude apps (web and desktop):** download `ETRANFischerEtAl2026.zip` from the [latest release](https://github.com/MarcoFischer1995/ETRANFischerEtAl2026/releases/latest). In Claude, open **Customize > Skills** and upload the zip. Code execution must be enabled.

**Claude Code:** clone this repository and copy the folder `etran-fischer-et-al-2026-paper` to `~/.claude/skills/` (all projects) or to `.claude/skills/` inside one project. Restart Claude Code.

```bash
git clone https://github.com/MarcoFischer1995/ETRANFischerEtAl2026.git
```

**Codex:** copy the same folder to `~/.agents/skills/`.

Then ask, for example:

- "Which vehicles, packs and cells were investigated, and how are the packs built?"
- "How much of the pack ohmic resistance comes from module connectors and the HVD?"
- "How well do summed cell resistances reproduce the measured pack resistance?"
- "Does the ohmic resistance identify the capacity-limiting logical cells?"

## Limitations

- The agent answers from the article only. It can still misread or over-generalize. Check important numbers against the [paper](https://doi.org/10.1016/j.etran.2026.100636).
- The study covers 3 packs of one vehicle model and one cell type. Its values characterize these systems and are not population-wide estimates for field-aged EV battery packs.
- The Euro 7 comparison in the article is numerical context only, not a compliance assessment. Field-operation histories of the vehicles were not available.
- Values printed inside figures exist only as images. Agents without image input cannot read them.
- Conversion status: `reviewed_with_limitations`. Every page was checked against the PDF, and the running text was rebuilt from the PDF's own text layer. The recorded limitations are parser differences only: equation transcriptions, table labels repeated for merged cells, a merged affiliation line, rejoined URLs and DOIs (and one date hyphen), check marks (✗) and two decimals misread by the second parser, and the calligraphic ℛ in ℛ<sub>p</sub>, which the PDF stores as a private-use glyph. The scientific content was not changed; one typo in the published article (SOH<sub>C,log.,cell,min</sub>, Section 4.2) is kept as printed. The only difference from the verified build is a more specific `description` in `SKILL.md`, which tells Claude when to use the skill (the Claude apps allow at most 200 characters).

## License and attribution

The article is published open access under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). This repository is an adaptation of that article. Text, figures and tables were converted to Markdown, JPEG and CSV. Layout artefacts were repaired, and equations were additionally transcribed as text. The scientific content was not modified. This repository is released under CC BY 4.0 as well, see `LICENSE`. Please cite the original article, see `CITATION.cff`.

Related paper agent: [JPSFischerEtAl2025](https://github.com/MarcoFischer1995/JPSFischerEtAl2025) for Fischer et al., *Journal of Power Sources* 656 (2025) 237921, the lab study on capacity fade and resistance increase in 814 cells that this field study refers to.

Conversion tool: Paper2Agent, J. Miao, J.R. Davis, Y. Zhang, J.K. Pritchard, J. Zou, *Reimagining research papers as interactive and reliable AI agents*, Nature (2026). https://doi.org/10.1038/s41586-026-11044-y

## Contact

Marco Fischer, Chair of Electrical Energy Storage Technology (EES), Technical University of Munich, marco.fischer@tum.de
