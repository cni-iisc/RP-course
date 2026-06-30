# KaTeX_EulerScript

`KaTeX_EulerScript-Regular.{woff,woff2}` provides Euler Script glyphs (the
style produced by LaTeX's `eucal` option to the `mathscr` package) for use
as a drop-in replacement of KaTeX's default `\mathscr` font.

## Provenance

Built directly from `eusm10.pfb` (AMS Euler Script Medium, 10pt), the
original Type 1 font shipped in TeX Live's `amsfonts` package — the exact
font this course's old LaTeX-built PDFs (`old-content/lecture-02.pdf`)
embed for `\mathscr`. Designed by Hermann Zapf for the American
Mathematical Society.

An earlier version of this file was built from MathJax's "Neo-Euler"
OpenType revival instead. That turned out to render noticeably more
ornate than the original AMS design (confirmed by extracting and comparing
the actual embedded font from `lecture-02.pdf`), so this version replaces
it with the authentic AMS outlines.

## How it was built

KaTeX renders `\mathscr{X}` as plain ASCII text (e.g. literal `"X"`) styled
via the CSS class `.katex .mathscr` — it has no notion of Type 1 fonts or
Unicode math codepoints, it just needs glyph outlines reachable at plain
ASCII `A`-`Z`.

`eusm10.pfb`'s charstrings could not be safely re-interpreted by common
Python/Adobe Type 1 parsers for this build (their outline extraction
diverged from how Ghostscript and Poppler/FreeType actually render the
font — verified by rasterizing the real PDF). To get outlines that are
verifiably correct, each glyph was instead produced via Ghostscript's own
`charpath` operator (`(eusm10.pfa) run ... (X) true charpath`), rendered to
a vector PDF (`-sDEVICE=pdfwrite`), and the resulting `m`/`l`/`c` path
operators were read back out of the PDF content stream and assembled into
a new CFF/OpenType font with `fontTools`. Advance widths come from the
font's own `eusm10.afm`. No glyph artwork was hand-edited.

## License

SIL Open Font License 1.1 — see `LICENSE.txt`. Per the OFL, the Reserved
Font Name `EUSM10` from the original is not used in this derivative.
