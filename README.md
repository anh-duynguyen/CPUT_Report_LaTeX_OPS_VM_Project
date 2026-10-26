# OPS260S Group 1 report – how to use this project

Compile with `latexmk -pdf main.tex` (or press **Recompile** in Overleaf; upload the whole folder / zip).

```
main.tex          preamble, title page, declarations, abstract, bibliography, appendix
chapters/         one file per chapter  (ch1_intro ... ch9_conclusion)  – edit only your own
images/           ALL screenshots
missing_images.txt  rewritten on every compile: the screenshots that are still missing
```

## Adding a screenshot to an existing slot
Every figure slot shows a dashed **SCREENSHOT PLACEHOLDER** box that names the file it is waiting for.
1. Save your screenshot into `images/` with **exactly** that file name (e.g. `remote_01.png`).
2. Recompile. The picture replaces the placeholder automatically – caption, numbering and cross-references stay.
3. `missing_images.txt` lists every slot that is still empty.

## Adding a new figure
Copy any `\shot` line in your chapter and change the three parts:

```latex
\shot{remote_04.png}{Caption of the figure}{fig:remote-04}
%      file in images/   caption text         unique label
```
Refer to it in the text with `\autoref{fig:remote-04}` (prints “Figure 6.4” and links to it).
Naming convention: `<chapter>_<NN>.png` – `install_`, `adds` (`ADDS_`), `dhcp_`, `dns_`, `gpo_`, `remote_`, `certs_`.
PNG or JPG both work. Labels must be unique across the whole report, so keep the chapter prefix.

## Writing your chapter
- DNS (`ch5_dns.tex`) and Remote Access (`ch7_remote.tex`) are skeletons; Certificate Services (`ch8_certs.tex`) is written in the same layout as the AD DS chapter. Replace each red **TODO** box with your text.
- Components you can reuse: `\section`/`\subsection`, a values table (see Table 3.1), `\begin{callout}{Title}...\end{callout}`, `\issue{title}{symptom}{fix}`, `lstlisting` for commands.
- Switch every TODO box off for the final version: put `\showtodofalse` in `main.tex` just before `\begin{document}`.

## References
Add a `\bibitem{key} ...` at the end of the bibliography list in `main.tex` (same format as the others) and cite with `\cite{key}`.
