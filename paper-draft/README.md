# EJP/ECP

## DESCRIPTION 

"ejpecp" is a LaTeX2e document class for typesetting articles for the 
mathematical research periodicals "Electronic Journal of Probability" (EJP) 
and "Electronic Communications in Probability" (ECP). The websites of these
electronic journals are https://imstat.org/journals-and-publications/electronic-journal-of-probability/

## COPYRIGHT

-   Copyright (c) 2019-2023 by Edgaras SAKURAS, VTeX, Lithuania for EJP-ECP
-   Copyright (c) 2018 by Deimantas GALCIUS, VTeX, Lithuania for EJP-ECP
-   Copyright (c) 2016-2017 by Eimantas GUMBAKIS, VTeX, Lithuania for EJP-ECP
-   Copyright (c) 2011-2015 by Krzysztof BURDZY and Djalil CHAFAI for EJP-ECP
-   The original ECP logo was designed when Ren\'e CARMONA was in charge of ECP
-   The original EJP logo was designed by Krzysztof BURDZY
-   The current \MR macro was provided by Martin HAIRER
-   The class internals benefited from the comments of S\'ebastien GOU\"EZEL
-   The `getmref.py` script is Copyright (c) 2017 S. TOLUSIS, J. PITMAN, L. TOLENE
-   The `getmref.py` script is free software licensed under the GPL
-   See https://www.e-publications.org/ims/support/batchmref.html

## FILE LIST

-   `sample.tex` - sample article for EJP or ECP (source file)
-   `sample.pdf` - sample article for EJP or ECP (PDF compiled)
-   `LPPL` - a copy of the LaTeX Project Public License
-   `README.md` - this file itself!
-   `getmref.py` - Python2 script to add MR URLs in bibliographies 
-   `ejpecp.cls` - class file 
-   `ejpecp.pdf` - class documentation

## INSTRUCTIONS FOR EJP-ECP AUTHORS

-   You only need `ejpecp.cls`, `sample.tex`, and `sample.pdf`
-   Take the time to read `sample.pdf`
-   Copy `sample.tex` into `yourname.tex`
-   Edit `yourname.tex` (update metadata and the content of the paper)
-   Be sure to have `ejpecp.cls` in the same directory (or any dir scanned for `cls`)
-   Compile `yourname.tex` with a `pdflatex` engine producing `yourname.pdf`
-   More detailed instructions for authors are available on Internet:
    -   EJP: https://imstat.org/journals-and-publications/electronic-journal-of-probability/
    -   ECP: https://imstat.org/journals-and-publications/electronic-communications-in-probability/

## DEPENDENCIES

`ejpecp` is a LaTeX2e document class designed to be used with a `pdflatex` engine.
`ejpecp` relies on the following packages: `amsmath`, `amsfonts`, `amssymb`, `amsthm`,
`bera`, `dsfont`, `hyperref`, `geometry`, `graphicx`, `latexsym`, `mathtools`, 
`microtype`, `afterpackage`. It was also successfully tested with the next 
generation engine `lualatex`.

## TROUBLESHOOTING

-   If You get an error after compilation (e.g. in MiKTeX v2.9):

        ! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.

    Try one of the following:

    1.  Add _Latin Modern_ font loading lines before the document class line:

            \RequirePackage{lmodern}
            \RequirePackage[T1]{fontenc}
            \documentclass[EJP]{ejpecp}

        It will change bitmap _Computer Modern_ fonts with scalable _Latin Modern_ fonts.

    2.  If 1st step does not solve the problem, then use `nofontexpansion` option:

        \documentclass[nofontexpansion,EJP]{ejpecp}

    It will turn off font expansion feature of `microtype` package. 

    **No worries**: font expansion will still be used at production stage.

-   If _Bitstream Vera_ font (i.e. `bera` package) is not available in Your TeX distribution, use `nobera` class option and add alternative main document font:

        \documentclass[nobera,EJP]{ejpecp}
        \usepackage{mathptmx}% URW Nimbus Roman
        \usepackage[T1]{fontenc}

    Some suggestions can be found here: https://www.tug.org/FontCatalogue/seriffonts.html

    **No worries**: `bera` package will still be used at production stage.

## LATEST VERSION

The latest version is on the CTAN at: 
https://www.ctan.org/pkg/ejpecp

Source code and development is on the GitHub at:
https://github.com/vtex-soft/texsupport.ims-ejpecp

## CHANGELOG

-   2023/12/18 v1.12.0
    -   author `\orcid` macro added
-   2021/11/04 v1.11.3
    -   Removed dash in MR
-   2021/09/07 v1.11.2
    -   Added `nobera` and `nofontexpansion` options
-   2021/08/17 v1.11.1
    -   Removed dependency on `lastpage` package
-   2021/04/20 v1.11.0
    -   preprint option added
-   2021/02/11 v1.10.0
    -   acks environment added and support macro
-   2020/10/21 v1.9.0
    -   Supplement environment added
-   2020/08/26 v1.8.3
    -   Updated URLs
-   2020/08/05
    -   Updated `getmref.py`
    -   Updated README and converted to Markdown syntax
-   2020/07/30 v1.8.2
    -   Updated AMS keywords to MSC2020 with url link
    -   Updated article no. prefix
-   2019/04/04 v1.7
    -   Merged changes with production version:
        -   `fixltx2e` dependency removed
        -   `natbib` setup with `afterpackage`
        -   cosmetic changes
-   2019/03/28 v1.6
    -   Full url doi links, new package maintainer, shorttitle info
-   2016/09/06 v1.5
    -   `hypertexnames=false` configuration for `hyperref` package
-   2016/04/06 v1.4
    -   Abstract baselineskip correction - paragraph ending inserted at the end of abstract
-   2016/02/23 v1.3
    -   Updated journal URLs and DOI output format
-   2015/12/23 v1.2
    -   Adapt `sample.tex` to EJMS/VTEX transition.
-   2014/12/13 v1.1
    -   Added class option `PSTRICKS` for problematic graphics
    -   Added Sébastien Gouëzel to `\ACKNO` in sample.tex
    -   Added load of `mathtools`, `fixltx2e`, `microtype` (suggested by Sébastien Gouëzel)
    -   Replaced `\begin/end{center}` by `\centering` for figure in `sample.tex` (idem)
    -   Removed `\makeatletter/other` from class file (idem)
    -   Removed `\ARXIVPASSWORD`
    -   Modified macro `\EMAIL` to allow special characters
-   2012/12/12 v1.0
    -   Added macro `\BEMAIL` for new lines in footnotes
    -   Added macro `\DEDICATORY` (suggested by Richard Bass)
    -   Added class option `NOAMS` for problematic papers
    -   Added trailing / in journal URL appearing in page foot
    -   Added support for `hyperref` pdftitle and other fields
    -   Added several environments derived from the theorem environment 
    -   Added more comments on `mgetmref.py` and on environments in `sample.tex`
    -   Added more comments on `\TITLE` and `\AUTHORS` in `sample.tex`
    -   Added reference list (bibliography) to table of contents and PDF support
    -   Added macro `\HALID` for Hyper Article en Ligne (French preprints)
    -   Fixed incorrect key spacing in bibliography (reported by Martin Hairer)
    -   Fixed `hyperref` options `pdfborder` and `colorlinks`
    -   Modified paragraph on source file preparation in `sample.tex` (clarification) 
    -   Modified margins (now left and right margins are identical)
    -   Modified headings (shorter paper reference, rational page number on foot)
    -   Modified "AMS Subject Classification 2010" into "AMS MSC 2010"
    -   Modified spacing after abstract for keywords, AMS-MSC, etc
-   2012/01/09 v0.57721
    -   Added `\EMAIL` macro and updated `sample.tex` accordingly
    -   Added environments "fact" and "notations" and updated `sample.tex`
    -   Modified headings, now DOI and ISSN are in first page headings
    -   Modified "Key words" into "Keywords"
    -   Modified ECP logo (length and width of horizontal rules)
-   2011/12/24 v0.5772
    -   Added dependency on `lastpage` package
    -   Modified `hyperref` options (no link borders + other tweaks)
    -   Modified `sample.tex` (page numbering and `lastpage`)
    -   Modified `\@PAGEEND` using `lastpage` package
    -   Removed  `\PAGESTART` and `\PAGEEND` from `sample.tex`
-   2011/12/12 v0.577 
    -   Added macro `\ACKNO`
    -   Added script `mgetmref.py` (suggested by Ph. Carmona)
    -   Modified `\MR` macro (thanks, Martin!) and removal of `xstring` dependency
    -   Modified `sample.tex` with more comments 
    -   Removed `\THANKS` in favor of the standard `\thanks`
-   2011/12/01 v0.57
    -   Added ISSN and support for DOI and for arXiv
    -   Added new class options "draft" and "final" (passed to the article class)
    -   Added customized `\thebibliography` with reduced `\itemsep` (due to `bera`)
    -   Added customized `\itemize` and `\enumerate` with reduced `\itemsep` (due to `bera`)
    -   Modified `\MR` (prints now "MR-#" instead of "MR #")
    -   Modified `sample.tex` (includes corrections after Anton's comments)
-   2011/11/26 v0.5
    -   Initial version

