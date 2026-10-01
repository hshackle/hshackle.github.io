# Editable CV

The source extracted from `../resume.zip` is maintained here. The original archive
is preserved. The current public PDF is `../pdfs/leynaShackletonCV.pdf`.
The historical main-source filename does not change the display name, Leyna Shackleton.

Build from this directory with an installed TeX distribution:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=../tmp/pdfs/build henryShackletonCV.tex
cp ../tmp/pdfs/build/henryShackletonCV.pdf ../pdfs/leynaShackletonCV.pdf
```

The native Codex LaTeX editor also confirmed successful compilation of the source.

## 2026-10-01 [codex] bibliography and rendering repair

Scope: supplied archive and bibliography records checked as of 2026-10-01.
Fixed the missing comma in the dissipative-spin-liquid entry, enabled preprints,
added the January 2026 Dirac spin-liquid preprint, updated the coding preprint
title, and ordered 2026 publications by publication date. Preprint years retain
the first-submission year. Protected the XDiag capitalization. Repaired wrapped
DOI links and changed DOI/arXiv links to HTTPS. Kept bibliography entries,
posters, and teaching content together across page breaks. Synchronized the two
outdated bibliography records in `../cv.md`.

Evidence inspected: [Dirac spin liquids](https://arxiv.org/abs/2601.19980),
[coding preprint v2](https://arxiv.org/abs/2503.15483),
[polaronic preprint v2](https://arxiv.org/abs/2408.02190),
[twisted quantum doubles](https://doi.org/10.1103/j6h1-hzyz),
[XDiag](https://arxiv.org/abs/2505.02901),
[chiral superconductor](https://arxiv.org/abs/2509.21591), and
[triangular antiferromagnets](https://arxiv.org/abs/2311.01572).
No journal reference was present in the three preprint records inspected.

Validation: successful latexmk/BibTeX build; successful native editor compilation;
all four final page images visually inspected, with no clipping or overlap;
15 published entries and three preprints checked in generated bibliographies;
all 15 distinct DOI links and all arXiv annotations checked for HTTPS and whitespace.
Only the moderncv icon fallback and a visually harmless title underfull-box warning remain.

Base revision: `4f0e8a8c40c19a58b03a412ab83b209bd9f0c11f`. Changes remain uncommitted and unpublished;
unrelated README/AGENTS changes were preserved. No scheduler or remote project applies.
Original archive SHA-256: `d8730b88ad84b5f43201424a8764902e1c44f86dc5e87026d4315e252b96dd3d`.
Final PDF SHA-256: `557b96577594c6af30e6c5487e3ec409d6ffd8cb09f8f6b8fd2b3cc537ec2b0c`.

Open issue / next action: a full talks/posters update is outside this repair.
The archive has different dates and fewer presentations than `cv.md`; verify
those shared records against event programs before synchronizing them.

## 2026-10-01 [codex] cleanup

Removed the redundant `resume-updated.zip` export after verifying every archived
file against the retained source and public PDF. The original supplied archive
and current CV were preserved. Added scoped ignore rules for future CV build
output. PDF checksum is unchanged; no recompilation was needed. Changes remain
uncommitted and unpublished. Next step remains the talks/posters verification above.

## 2026-10-01 [codex] presentation maintenance

Scope: targeted presentation review, September 2025 through October 2026,
including the confirmed October 20 NYU seminar. Older website talks were
reconciled with the PDF CV; this was not a full historical or poster audit.
Added KITP and two Minnesota talks, the upcoming NYU seminar, and six slide PDFs
(KITP, Minnesota seminar/colloquium, Nordita, Pappalardo, Rutgers). Corrected the
MIT and Harvard Kids talks to September 2025 as confirmed by the user. Used the
user-confirmed Minnesota seminar date/title, September 25 and “Anyonic neural
quantum states”; the supplied slide cover retains its earlier preparation date.
Used the user-selected KITP program title, “Neural-Network Variational Monte
Carlo for Anyons.” Restored four 2024 talks omitted from the imported PDF CV,
using the website's month-level dates, and added all existing slide links to
that CV. Preserved the completed bibliography repair.

Public evidence inspected: [KITP program](https://online.kitp.ucsb.edu/online/aiqmatter-c26/),
[NYU seminars](https://physics.nyu.edu/events.html?EventsPage=cqp),
[Nordita timetable](https://indico.fysik.su.se/event/9148/timetable/?print=1&view=standard_inline_minutes),
[MIT Pappalardo symposium](https://physics.mit.edu/research/pappalardo-fellowships-in-physics/pappalardo-symposium/),
[Rutgers conference](https://cmsr.rutgers.edu/newsevents-cmsr/event-details/1370-130th-statistical-mechanics-conference),
[APS abstract](https://meetings-archive.aps.org/smt/2026/mar-m45/8/), and
[NUS seminars](https://sites.google.com/view/nuscmseminars/home/upcoming-previous).
Relevant correspondence and supplied title pages supplemented those records;
private correspondence is not retained in this repository.

Slide exports: retained supplied PDFs for four events. Used local PowerPoint
printing exports for Pappalardo and Minnesota seminar, with notes excluded.
Removed the Pappalardo chat screenshot at the user's direction and flattened
its final animation states to avoid overlapping objects. Restored two Minnesota
EMF diagrams from the corresponding supplied figure PDFs to fix export loss.
Supplied originals were preserved; videos/animations become static PDF content.

Validation: successful documented latexmk/BibTeX and Franklin builds; five CV
pages visually inspected, with presentation pages rechecked after the final
correction; slide decks rendered and scanned, with repaired pages inspected at
full size; website presentation layout inspected in Chrome. All 29 presentation
records and 23 slide links agree between the website and PDF CV, and every
local slide target exists. No private staging directory, archive, editable CV
source or guidelines were copied into the generated site. Optional website
minification was unavailable locally; the build completed successfully.

Base revision: `4f0e8a8c40c19a58b03a412ab83b209bd9f0c11f`, local `main`;
existing CV repair and website-guideline changes are retained in this maintenance
commit. No remote scientific project or scheduler applies. Publication is via
the authorized push to `main`, the existing Franklin workflow, and `gh-pages`;
live deployment verification follows the push.
Final CV SHA-256: `81141187b39741abbbb9c297a375eca6bdd13fe6a8fd6f6b07accaff3dbfb8e6`.

Open issue / next action: posters remain outside this presentation pass. At the
next poster update, verify the stale June 2026 upcoming entry and reconcile the
Ultra-Quantum Matter date and poster coverage between the two CV versions.

Deployment follow-up: the first successful workflow carried forward the tracked
CV HTML instead of regenerating it, although it copied the new slide assets.
Changed the Franklin deployment call to `optimize(clear=true)` so each publish
regenerates the output from source. The local clean build regenerated the final
CV page and excluded private working files; live checks follow the corrected
deployment.

The clean rebuild alone did not resolve publication. Inspection of the deploy
action log identified its forced checkout of the source revision, which resets
tracked `__site` files after the build. The workflow now preserves the generated
website in an ignored `.deploy-site` directory before invoking that action.
The staging directory is also excluded from Franklin inputs. A bounded Git
fixture reproduced the overwrite and confirmed that the untracked snapshot
survives it. The supplied assets and editable sources remain unchanged.
