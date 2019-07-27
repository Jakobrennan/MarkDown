<div id="doc" class="container-fluid">

<div id="flattr">

[](https://pandoc.org){.FlattrButton}
[![Flattr
this](https://api.flattr.com/button/flattr-badge-large.png "Flattr this")](https://flattr.com/thing/936364/Pandoc)

</div>

<div id="paypal">

![](https://www.paypalobjects.com/en_US/i/scr/pixel.gif){width="1"
height="1"}

</div>

<span class="big">Pandoc</span>   <span class="small">a universal
document converter</span>
<div id="bd">

<div class="navbar-header">

<span class="sr-only">Toggle navigation</span> <span
class="icon-bar"></span> <span class="icon-bar"></span> <span
class="icon-bar"></span>

</div>

<div class="navbar-collapse collapse">

-   [About](index.html)
-   [Installing](installing.html)
-   [Getting started](getting-started.html)
-   [Demos](#){#demobtn .tree-toggle .nav-header}
    -   [Try pandoc online](try)
    -   [Examples](demos.html)
-   [Documentation](#){#docbtn .tree-toggle .nav-header}
    -   [User's Guide](MANUAL.html)
    -   [User's Guide (PDF)](MANUAL.pdf)
    -   [Making an ebook](epub.html)
    -   [Filters](filters.html)
    -   [Lua filters](lua-filters.html)
    -   [Contributing](CONTRIBUTING.html)
    -   [FAQ](faqs.html)
    -   [Press](press.html)
    -   [Emacs Org mode support details](org.html)
    -   [Using the Pandoc API](using-the-pandoc-api.html)
    -   [API documentation](http://hackage.haskell.org/package/pandoc)
-   [Help](help.html)
-   [Extras](https://github.com/jgm/pandoc/wiki/Pandoc-Extras)
-   [Releases](releases.html)

</div>

<div class="row">

<div id="toc">

-   [Synopsis](#synopsis)
-   [Description](#description)
    -   [Using pandoc](#using-pandoc)
    -   [Specifying formats](#specifying-formats)
    -   [Character encoding](#character-encoding)
    -   [Creating a PDF](#creating-a-pdf)
    -   [Reading from the Web](#reading-from-the-web)
-   [Options](#options)
    -   [General options](#general-options)
    -   [Reader options](#reader-options)
    -   [General writer options](#general-writer-options)
    -   [Options affecting specific
        writers](#options-affecting-specific-writers)
    -   [Citation rendering](#citation-rendering)
    -   [Math rendering in HTML](#math-rendering-in-html)
    -   [Options for wrapper scripts](#options-for-wrapper-scripts)
-   [Templates](#templates)
    -   [Metadata variables](#metadata-variables)
    -   [Language variables](#language-variables)
    -   [Variables for HTML slides](#variables-for-html-slides)
    -   [Variables for Beamer slides](#variables-for-beamer-slides)
    -   [Variables for LaTeX](#variables-for-latex)
        -   [Layout](#layout)
        -   [Fonts](#fonts)
        -   [Links](#links)
        -   [Front matter](#front-matter)
        -   [BibLaTeX Bibliographies](#biblatex-bibliographies)
    -   [Variables for ConTeXt](#variables-for-context)
    -   [Variables for <span
        class="nowrap">`wkhtmltopdf`</span>](#variables-for-wkhtmltopdf)
    -   [Variables for man pages](#variables-for-man-pages)
    -   [Variables for ms](#variables-for-ms)
    -   [Structural variables](#structural-variables)
    -   [Using variables in templates](#using-variables-in-templates)
-   [Extensions](#extensions)
    -   [Typography](#typography)
    -   [Headings and sections](#headings-and-sections)
    -   [Math Input](#math-input)
    -   [Raw HTML/TeX](#raw-htmltex)
    -   [Literate Haskell support](#literate-haskell-support)
    -   [Other extensions](#other-extensions)
-   [Pandoc’s Markdown](#pandocs-markdown)
    -   [Philosophy](#philosophy)
    -   [Paragraphs](#paragraphs)
    -   [Headings](#headings)
        -   [Setext-style headings](#setext-style-headings)
        -   [ATX-style headings](#atx-style-headings)
        -   [Heading identifiers](#heading-identifiers)
    -   [Block quotations](#block-quotations)
    -   [Verbatim (code) blocks](#verbatim-code-blocks)
        -   [Indented code blocks](#indented-code-blocks)
        -   [Fenced code blocks](#fenced-code-blocks)
    -   [Line blocks](#line-blocks)
    -   [Lists](#lists)
        -   [Bullet lists](#bullet-lists)
        -   [Block content in list items](#block-content-in-list-items)
        -   [Ordered lists](#ordered-lists)
        -   [Definition lists](#definition-lists)
        -   [Numbered example lists](#numbered-example-lists)
        -   [Compact and loose lists](#compact-and-loose-lists)
        -   [Ending a list](#ending-a-list)
    -   [Horizontal rules](#horizontal-rules)
    -   [Tables](#tables)
    -   [Metadata blocks](#metadata-blocks)
    -   [Backslash escapes](#backslash-escapes)
    -   [Inline formatting](#inline-formatting)
        -   [Emphasis](#emphasis)
        -   [Strikeout](#strikeout)
        -   [Superscripts and subscripts](#superscripts-and-subscripts)
        -   [Verbatim](#verbatim)
        -   [Small caps](#small-caps)
    -   [Math](#math)
    -   [Raw HTML](#raw-html)
        -   [Generic raw attribute](#generic-raw-attribute)
    -   [LaTeX macros](#latex-macros)
    -   [Links](#links-1)
        -   [Automatic links](#automatic-links)
        -   [Inline links](#inline-links)
        -   [Reference links](#reference-links)
        -   [Internal links](#internal-links)
    -   [Images](#images)
    -   [Divs and Spans](#divs-and-spans)
    -   [Footnotes](#footnotes)
    -   [Citations](#citations)
    -   [Non-pandoc extensions](#non-pandoc-extensions)
    -   [Markdown variants](#markdown-variants)
-   [Producing slide shows with
    pandoc](#producing-slide-shows-with-pandoc)
    -   [Structuring the slide show](#structuring-the-slide-show)
    -   [Incremental lists](#incremental-lists)
    -   [Inserting pauses](#inserting-pauses)
    -   [Styling the slides](#styling-the-slides)
    -   [Speaker notes](#speaker-notes)
    -   [Columns](#columns)
    -   [Frame attributes in beamer](#frame-attributes-in-beamer)
    -   [Background in reveal.js and
        beamer](#background-in-reveal.js-and-beamer)
-   [Creating EPUBs with pandoc](#creating-epubs-with-pandoc)
    -   [EPUB Metadata](#epub-metadata)
    -   [The <span class="nowrap">`epub:type`</span>
        attribute](#the-epubtype-attribute)
    -   [Linked media](#linked-media)
-   [Creating Jupyter notebooks with
    pandoc](#creating-jupyter-notebooks-with-pandoc)
-   [Syntax highlighting](#syntax-highlighting)
-   [Custom Styles](#custom-styles)
    -   [Output](#output)
    -   [Input](#input)
-   [Custom writers](#custom-writers)
-   [A note on security](#a-note-on-security)
-   [Authors](#authors)

</div>

Synopsis
========

<span class="nowrap">`pandoc`</span> \[*options*\] \[*input-file*\]…

Description
===========

Pandoc is a [Haskell](https://www.haskell.org) library for converting
from one markup format to another, and a command-line tool that uses
this library.

Pandoc can convert between numerous markup and word processing formats,
including, but not limited to, various flavors of
[Markdown](http://daringfireball.net/projects/markdown/),
[HTML](http://www.w3.org/html/), [LaTeX](http://latex-project.org) and
[Word docx](https://en.wikipedia.org/wiki/Office_Open_XML). For the full
lists of input and output formats, see the [<span
class="nowrap">`--from`</span>](#option--from){.option} and [<span
class="nowrap">`--to`</span>](#option--to){.option} [options
below](#general-options). Pandoc can also produce
[PDF](https://www.adobe.com/pdf/) output: see [creating a
PDF](#creating-a-pdf), below.

Pandoc’s enhanced version of Markdown includes syntax for
[tables](#tables), [definition lists](#definition-lists), [metadata
blocks](#metadata-blocks), [footnotes](#footnotes),
[citations](#citations), [math](#math), and much more. See below under
[Pandoc’s Markdown](#pandocs-markdown).

Pandoc has a modular design: it consists of a set of readers, which
parse text in a given format and produce a native representation of the
document (an *abstract syntax tree* or AST), and a set of writers, which
convert this native representation into a target format. Thus, adding an
input or output format requires only adding a reader or writer. Users
can also run custom [pandoc filters](http://pandoc.org/filters.html) to
modify the intermediate AST.

Because pandoc’s intermediate representation of a document is less
expressive than many of the formats it converts between, one should not
expect perfect conversions between every format and every other. Pandoc
attempts to preserve the structural elements of a document, but not
formatting details such as margin size. And some document elements, such
as complex tables, may not fit into pandoc’s simple document model.
While conversions from pandoc’s Markdown to all formats aspire to be
perfect, conversions from formats more expressive than pandoc’s Markdown
can be expected to be lossy.

Using pandoc
------------

If no *input-files* are specified, input is read from *stdin*. Output
goes to *stdout* by default. For output to a file, use the [<span
class="nowrap">`-o`</span>](#option--output){.option} option:

    pandoc -o output.html input.txt

By default, pandoc produces a document fragment. To produce a standalone
document (e.g. a valid HTML file including <span
class="nowrap">`<head>`</span> and <span
class="nowrap">`<body>`</span>), use the [<span
class="nowrap">`-s`</span>](#option--standalone){.option} or [<span
class="nowrap">`--standalone`</span>](#option--standalone){.option}
flag:

    pandoc -s -o output.html input.txt

For more information on how standalone documents are produced, see
[Templates](#templates) below.

If multiple input files are given, <span class="nowrap">`pandoc`</span>
will concatenate them all (with blank lines between them) before
parsing. (Use [<span
class="nowrap">`--file-scope`</span>](#option--file-scope){.option} to
parse files individually.)

Specifying formats
------------------

The format of the input and output can be specified explicitly using
command-line options. The input format can be specified using the [<span
class="nowrap">`-f/--from`</span>](#option--from){.option} option, the
output format using the [<span
class="nowrap">`-t/--to`</span>](#option--to){.option} option. Thus, to
convert <span class="nowrap">`hello.txt`</span> from Markdown to LaTeX,
you could type:

    pandoc -f markdown -t latex hello.txt

To convert <span class="nowrap">`hello.html`</span> from HTML to
Markdown:

    pandoc -f html -t markdown hello.html

Supported input and output formats are listed below under
[Options](#options) (see [<span
class="nowrap">`-f`</span>](#option--from){.option} for input formats
and [<span class="nowrap">`-t`</span>](#option--to){.option} for output
formats). You can also use <span
class="nowrap">`pandoc --list-input-formats`</span> and <span
class="nowrap">`pandoc --list-output-formats`</span> to print lists of
supported formats.

If the input or output format is not specified explicitly, <span
class="nowrap">`pandoc`</span> will attempt to guess it from the
extensions of the filenames. Thus, for example,

    pandoc -o hello.tex hello.txt

will convert <span class="nowrap">`hello.txt`</span> from Markdown to
LaTeX. If no output file is specified (so that output goes to *stdout*),
or if the output file’s extension is unknown, the output format will
default to HTML. If no input file is specified (so that input comes from
*stdin*), or if the input files’ extensions are unknown, the input
format will be assumed to be Markdown.

Character encoding
------------------

Pandoc uses the UTF-8 character encoding for both input and output. If
your local character encoding is not UTF-8, you should pipe input and
output through [<span
class="nowrap">`iconv`</span>](http://www.gnu.org/software/libiconv/):

    iconv -t utf-8 input.txt | pandoc | iconv -f utf-8

Note that in some output formats (such as HTML, LaTeX, ConTeXt, RTF,
OPML, DocBook, and Texinfo), information about the character encoding is
included in the document header, which will only be included if you use
the [<span
class="nowrap">`-s/--standalone`</span>](#option--standalone){.option}
option.

Creating a PDF
--------------

To produce a PDF, specify an output file with a <span
class="nowrap">`.pdf`</span> extension:

    pandoc test.txt -o test.pdf

By default, pandoc will use LaTeX to create the PDF, which requires that
a LaTeX engine be installed (see [<span
class="nowrap">`--pdf-engine`</span>](#option--pdf-engine){.option}
below).

Alternatively, pandoc can use [ConTeXt](http://www.contextgarden.net/),
<span class="nowrap">`pdfroff`</span>, or any of the following
HTML/CSS-to-PDF-engines, to create a PDF: [<span
class="nowrap">`wkhtmltopdf`</span>](https://wkhtmltopdf.org), [<span
class="nowrap">`weasyprint`</span>](http://weasyprint.org) or [<span
class="nowrap">`prince`</span>](https://www.princexml.com/). To do this,
specify an output file with a <span class="nowrap">`.pdf`</span>
extension, as before, but add the [<span
class="nowrap">`--pdf-engine`</span>](#option--pdf-engine){.option}
option or [<span
class="nowrap">`-t context`</span>](#option--to){.option}, [<span
class="nowrap">`-t html`</span>](#option--to){.option}, or [<span
class="nowrap">`-t ms`</span>](#option--to){.option} to the command line
([<span class="nowrap">`-t html`</span>](#option--to){.option} defaults
to [<span
class="nowrap">`--pdf-engine=wkhtmltopdf`</span>](#option--pdf-engine){.option}).

PDF output uses [variables for LaTeX](#variables-for-latex) (with a
LaTeX engine); [variables for ConTeXt](#variables-for-context) (with
ConTeXt); or [variables for <span
class="nowrap">`wkhtmltopdf`</span>](#variables-for-wkhtmltopdf) (an
HTML/CSS-to-PDF engine; [<span
class="nowrap">`--css`</span>](#option--css){.option} also affects the
output).

To debug the PDF creation, it can be useful to look at the intermediate
representation: instead of [<span
class="nowrap">`-o test.pdf`</span>](#option--output){.option}, use for
example [<span
class="nowrap">`-s -o test.tex`</span>](#option--standalone){.option} to
output the generated LaTeX. You can then test it with <span
class="nowrap">`pdflatex test.tex`</span>.

When using LaTeX, the following packages need to be available (they are
included with all recent versions of [TeX
Live](http://www.tug.org/texlive/)): [<span
class="nowrap">`amsfonts`</span>](https://ctan.org/pkg/amsfonts), [<span
class="nowrap">`amsmath`</span>](https://ctan.org/pkg/amsmath), [<span
class="nowrap">`lm`</span>](https://ctan.org/pkg/lm), [<span
class="nowrap">`unicode-math`</span>](https://ctan.org/pkg/unicode-math),
[<span class="nowrap">`ifxetex`</span>](https://ctan.org/pkg/ifxetex),
[<span class="nowrap">`ifluatex`</span>](https://ctan.org/pkg/ifluatex),
[<span class="nowrap">`listings`</span>](https://ctan.org/pkg/listings)
(if the [<span
class="nowrap">`--listings`</span>](#option--listings){.option} option
is used), [<span
class="nowrap">`fancyvrb`</span>](https://ctan.org/pkg/fancyvrb), [<span
class="nowrap">`longtable`</span>](https://ctan.org/pkg/longtable),
[<span class="nowrap">`booktabs`</span>](https://ctan.org/pkg/booktabs),
[<span class="nowrap">`graphicx`</span>](https://ctan.org/pkg/graphicx)
and [<span
class="nowrap">`grffile`</span>](https://ctan.org/pkg/grffile) (if the
document contains images), [<span
class="nowrap">`hyperref`</span>](https://ctan.org/pkg/hyperref), [<span
class="nowrap">`xcolor`</span>](https://ctan.org/pkg/xcolor), [<span
class="nowrap">`ulem`</span>](https://ctan.org/pkg/ulem), [<span
class="nowrap">`geometry`</span>](https://ctan.org/pkg/geometry) (with
the <span class="nowrap">`geometry`</span> variable set), [<span
class="nowrap">`setspace`</span>](https://ctan.org/pkg/setspace) (with
<span class="nowrap">`linestretch`</span>), and [<span
class="nowrap">`babel`</span>](https://ctan.org/pkg/babel) (with <span
class="nowrap">`lang`</span>). The use of <span
class="nowrap">`xelatex`</span> or <span
class="nowrap">`lualatex`</span> as the PDF engine requires [<span
class="nowrap">`fontspec`</span>](https://ctan.org/pkg/fontspec). <span
class="nowrap">`xelatex`</span> uses [<span
class="nowrap">`polyglossia`</span>](https://ctan.org/pkg/polyglossia)
(with <span class="nowrap">`lang`</span>), [<span
class="nowrap">`xecjk`</span>](https://ctan.org/pkg/xecjk), and [<span
class="nowrap">`bidi`</span>](https://ctan.org/pkg/bidi) (with the <span
class="nowrap">`dir`</span> variable set). If the <span
class="nowrap">`mathspec`</span> variable is set, <span
class="nowrap">`xelatex`</span> will use [<span
class="nowrap">`mathspec`</span>](https://ctan.org/pkg/mathspec) instead
of [<span
class="nowrap">`unicode-math`</span>](https://ctan.org/pkg/unicode-math).
The [<span
class="nowrap">`upquote`</span>](https://ctan.org/pkg/upquote) and
[<span
class="nowrap">`microtype`</span>](https://ctan.org/pkg/microtype)
packages are used if available, and [<span
class="nowrap">`csquotes`</span>](https://ctan.org/pkg/csquotes) will be
used for [typography](#typography) if <span
class="nowrap">`\usepackage{csquotes}`</span> is present in the template
or included via <span class="nowrap">`/H/--include-in-header`</span>.
The [<span class="nowrap">`natbib`</span>](https://ctan.org/pkg/natbib),
[<span class="nowrap">`biblatex`</span>](https://ctan.org/pkg/biblatex),
[<span class="nowrap">`bibtex`</span>](https://ctan.org/pkg/bibtex), and
[<span class="nowrap">`biber`</span>](https://ctan.org/pkg/biber)
packages can optionally be used for [citation
rendering](#citation-rendering). The following packages will be used to
improve output quality if present, but pandoc does not require them to
be present: [<span
class="nowrap">`upquote`</span>](https://ctan.org/pkg/upquote) (for
straight quotes in verbatim environments), [<span
class="nowrap">`microtype`</span>](https://ctan.org/pkg/microtype) (for
better spacing adjustments), [<span
class="nowrap">`parskip`</span>](https://ctan.org/pkg/parskip) (for
better inter-paragraph spaces), [<span
class="nowrap">`xurl`</span>](https://ctan.org/pkg/xurl) (for better
line breaks in URLs), [<span
class="nowrap">`bookmark`</span>](https://ctan.org/pkg/bookmark) (for
better PDF bookmarks), and [<span
class="nowrap">`footnotehyper`</span>](https://ctan.org/pkg/footnotehyper)
or [<span
class="nowrap">`footnote`</span>](https://ctan.org/pkg/footnote) (to
allow footnotes in tables).

Reading from the Web
--------------------

Instead of an input file, an absolute URI may be given. In this case
pandoc will fetch the content using HTTP:

    pandoc -f html -t markdown http://www.fsf.org

It is possible to supply a custom User-Agent string or other header when
requesting a document from a URL:

    pandoc -f html -t markdown --request-header User-Agent:"Mozilla/5.0" \
      http://www.fsf.org

Options
=======

General options {#general-options .options}
---------------

<span id="option--from" class="option-anchor"><span class="nowrap">`-f`{.option-def}</span> *FORMAT*, <span class="nowrap">`-r`{.option-def}</span> *FORMAT*, <span class="nowrap">`--from=`{.option-def}</span>*FORMAT*, <span class="nowrap">`--read=`{.option-def}</span>*FORMAT*</span>

:   Specify input format. *FORMAT* can be:

    <div id="input-formats">

    -   <span class="nowrap">`commonmark`</span>
        ([CommonMark](http://commonmark.org) Markdown)
    -   <span class="nowrap">`creole`</span> ([Creole
        1.0](http://www.wikicreole.org/wiki/Creole1.0))
    -   <span class="nowrap">`docbook`</span>
        ([DocBook](http://docbook.org))
    -   <span class="nowrap">`docx`</span> ([Word
        docx](https://en.wikipedia.org/wiki/Office_Open_XML))
    -   <span class="nowrap">`dokuwiki`</span> ([DokuWiki
        markup](https://www.dokuwiki.org/dokuwiki))
    -   <span class="nowrap">`epub`</span>
        ([EPUB](http://idpf.org/epub))
    -   <span class="nowrap">`fb2`</span>
        ([FictionBook2](http://www.fictionbook.org/index.php/Eng:XML_Schema_Fictionbook_2.1) e-book)
    -   <span class="nowrap">`gfm`</span> ([GitHub-Flavored
        Markdown](https://help.github.com/articles/github-flavored-markdown/)),
        or the deprecated and less accurate <span
        class="nowrap">`markdown_github`</span>; use [<span
        class="nowrap">`markdown_github`</span>](#markdown-variants)
        only if you need extensions not supported in [<span
        class="nowrap">`gfm`</span>](#markdown-variants).
    -   <span class="nowrap">`haddock`</span> ([Haddock
        markup](https://www.haskell.org/haddock/doc/html/ch03s08.html))
    -   <span class="nowrap">`html`</span>
        ([HTML](http://www.w3.org/html/))
    -   <span class="nowrap">`ipynb`</span> ([Jupyter
        notebook](https://nbformat.readthedocs.io/en/latest/))
    -   <span class="nowrap">`jats`</span>
        ([JATS](https://jats.nlm.nih.gov) XML)
    -   <span class="nowrap">`json`</span> (JSON version of native AST)
    -   <span class="nowrap">`latex`</span>
        ([LaTeX](http://latex-project.org))
    -   <span class="nowrap">`markdown`</span> ([Pandoc’s
        Markdown](#pandocs-markdown))
    -   <span class="nowrap">`markdown_mmd`</span>
        ([MultiMarkdown](http://fletcherpenney.net/multimarkdown/))
    -   <span class="nowrap">`markdown_phpextra`</span> ([PHP Markdown
        Extra](https://michelf.ca/projects/php-markdown/extra/))
    -   <span class="nowrap">`markdown_strict`</span> (original
        unextended
        [Markdown](http://daringfireball.net/projects/markdown/))
    -   <span class="nowrap">`mediawiki`</span> ([MediaWiki
        markup](https://www.mediawiki.org/wiki/Help:Formatting))
    -   <span class="nowrap">`man`</span> ([roff
        man](http://man7.org/linux/man-pages/man7/groff_man.7.html))
    -   <span class="nowrap">`muse`</span>
        ([Muse](https://amusewiki.org/library/manual))
    -   <span class="nowrap">`native`</span> (native Haskell)
    -   <span class="nowrap">`odt`</span>
        ([ODT](http://en.wikipedia.org/wiki/OpenDocument))
    -   <span class="nowrap">`opml`</span>
        ([OPML](http://dev.opml.org/spec2.html))
    -   <span class="nowrap">`org`</span> ([Emacs Org
        mode](http://orgmode.org))
    -   <span class="nowrap">`rst`</span>
        ([reStructuredText](http://docutils.sourceforge.net/docs/ref/rst/introduction.html))
    -   <span class="nowrap">`t2t`</span>
        ([txt2tags](http://txt2tags.org))
    -   <span class="nowrap">`textile`</span>
        ([Textile](http://redcloth.org/textile))
    -   <span class="nowrap">`tikiwiki`</span> ([TikiWiki
        markup](https://doc.tiki.org/Wiki-Syntax-Text#The_Markup_Language_Wiki-Syntax))
    -   <span class="nowrap">`twiki`</span> ([TWiki
        markup](http://twiki.org/cgi-bin/view/TWiki/TextFormattingRules))
    -   <span class="nowrap">`vimwiki`</span>
        ([Vimwiki](https://vimwiki.github.io))

    </div>

    Extensions can be individually enabled or disabled by appending
    <span class="nowrap">`+EXTENSION`</span> or <span
    class="nowrap">`-EXTENSION`</span> to the format name. See
    [Extensions](#extensions) below, for a list of extensions and
    their names. See [<span
    class="nowrap">`--list-input-formats`</span>](#option--list-input-formats){.option}
    and [<span
    class="nowrap">`--list-extensions`</span>](#option--list-extensions){.option}, below.

<span id="option--to" class="option-anchor"><span class="nowrap">`-t`{.option-def}</span> *FORMAT*, <span class="nowrap">`-w`{.option-def}</span> *FORMAT*, <span class="nowrap">`--to=`{.option-def}</span>*FORMAT*, <span class="nowrap">`--write=`{.option-def}</span>*FORMAT*</span>

:   Specify output format. *FORMAT* can be:

    <div id="output-formats">

    -   <span class="nowrap">`asciidoc`</span>
        ([AsciiDoc](http://www.methods.co.nz/asciidoc/)) or <span
        class="nowrap">`asciidoctor`</span>
        ([AsciiDoctor](https://asciidoctor.org/))
    -   <span class="nowrap">`beamer`</span> ([LaTeX
        beamer](https://ctan.org/pkg/beamer) slide show)
    -   <span class="nowrap">`commonmark`</span>
        ([CommonMark](http://commonmark.org) Markdown)
    -   <span class="nowrap">`context`</span>
        ([ConTeXt](http://www.contextgarden.net/))
    -   <span class="nowrap">`docbook`</span> or <span
        class="nowrap">`docbook4`</span>
        ([DocBook](http://docbook.org) 4)
    -   <span class="nowrap">`docbook5`</span> (DocBook 5)
    -   <span class="nowrap">`docx`</span> ([Word
        docx](https://en.wikipedia.org/wiki/Office_Open_XML))
    -   <span class="nowrap">`dokuwiki`</span> ([DokuWiki
        markup](https://www.dokuwiki.org/dokuwiki))
    -   <span class="nowrap">`epub`</span> or <span
        class="nowrap">`epub3`</span> ([EPUB](http://idpf.org/epub)
        v3 book)
    -   <span class="nowrap">`epub2`</span> (EPUB v2)
    -   <span class="nowrap">`fb2`</span>
        ([FictionBook2](http://www.fictionbook.org/index.php/Eng:XML_Schema_Fictionbook_2.1) e-book)
    -   <span class="nowrap">`gfm`</span> ([GitHub-Flavored
        Markdown](https://help.github.com/articles/github-flavored-markdown/)),
        or the deprecated and less accurate <span
        class="nowrap">`markdown_github`</span>; use [<span
        class="nowrap">`markdown_github`</span>](#markdown-variants)
        only if you need extensions not supported in [<span
        class="nowrap">`gfm`</span>](#markdown-variants).
    -   <span class="nowrap">`haddock`</span> ([Haddock
        markup](https://www.haskell.org/haddock/doc/html/ch03s08.html))
    -   <span class="nowrap">`html`</span> or <span
        class="nowrap">`html5`</span> ([HTML](http://www.w3.org/html/),
        i.e. [HTML5](http://www.w3.org/TR/html5/)/XHTML [polyglot
        markup](https://www.w3.org/TR/html-polyglot/))
    -   <span class="nowrap">`html4`</span>
        ([XHTML](http://www.w3.org/TR/xhtml1/) 1.0 Transitional)
    -   <span class="nowrap">`icml`</span> ([InDesign
        ICML](http://wwwimages.adobe.com/www.adobe.com/content/dam/acom/en/devnet/indesign/sdk/cs6/idml/idml-cookbook.pdf))
    -   <span class="nowrap">`ipynb`</span> ([Jupyter
        notebook](https://nbformat.readthedocs.io/en/latest/))
    -   <span class="nowrap">`jats`</span>
        ([JATS](https://jats.nlm.nih.gov) XML)
    -   <span class="nowrap">`jira`</span>
        ([Jira](https://jira.atlassian.com/secure/WikiRendererHelpAction.jspa?section=all)
        wiki markup)
    -   <span class="nowrap">`json`</span> (JSON version of native AST)
    -   <span class="nowrap">`latex`</span>
        ([LaTeX](http://latex-project.org))
    -   <span class="nowrap">`man`</span> ([roff
        man](http://man7.org/linux/man-pages/man7/groff_man.7.html))
    -   <span class="nowrap">`markdown`</span> ([Pandoc’s
        Markdown](#pandocs-markdown))
    -   <span class="nowrap">`markdown_mmd`</span>
        ([MultiMarkdown](http://fletcherpenney.net/multimarkdown/))
    -   <span class="nowrap">`markdown_phpextra`</span> ([PHP Markdown
        Extra](https://michelf.ca/projects/php-markdown/extra/))
    -   <span class="nowrap">`markdown_strict`</span> (original
        unextended
        [Markdown](http://daringfireball.net/projects/markdown/))
    -   <span class="nowrap">`mediawiki`</span> ([MediaWiki
        markup](https://www.mediawiki.org/wiki/Help:Formatting))
    -   <span class="nowrap">`ms`</span> ([roff
        ms](http://man7.org/linux/man-pages/man7/groff_ms.7.html))
    -   <span class="nowrap">`muse`</span>
        ([Muse](https://amusewiki.org/library/manual)),
    -   <span class="nowrap">`native`</span> (native Haskell),
    -   <span class="nowrap">`odt`</span> ([OpenOffice text
        document](http://en.wikipedia.org/wiki/OpenDocument))
    -   <span class="nowrap">`opml`</span>
        ([OPML](http://dev.opml.org/spec2.html))
    -   <span class="nowrap">`opendocument`</span>
        ([OpenDocument](http://opendocument.xml.org))
    -   <span class="nowrap">`org`</span> ([Emacs Org
        mode](http://orgmode.org))
    -   <span class="nowrap">`plain`</span> (plain text),
    -   <span class="nowrap">`pptx`</span>
        ([PowerPoint](https://en.wikipedia.org/wiki/Microsoft_PowerPoint)
        slide show)
    -   <span class="nowrap">`rst`</span>
        ([reStructuredText](http://docutils.sourceforge.net/docs/ref/rst/introduction.html))
    -   <span class="nowrap">`rtf`</span> ([Rich Text
        Format](http://en.wikipedia.org/wiki/Rich_Text_Format))
    -   <span class="nowrap">`texinfo`</span> ([GNU
        Texinfo](http://www.gnu.org/software/texinfo/))
    -   <span class="nowrap">`textile`</span>
        ([Textile](http://redcloth.org/textile))
    -   <span class="nowrap">`slideous`</span>
        ([Slideous](http://goessner.net/articles/slideous/) HTML and
        JavaScript slide show)
    -   <span class="nowrap">`slidy`</span>
        ([Slidy](http://www.w3.org/Talks/Tools/Slidy/) HTML and
        JavaScript slide show)
    -   <span class="nowrap">`dzslides`</span>
        ([DZSlides](http://paulrouget.com/dzslides/) HTML5 + JavaScript
        slide show),
    -   <span class="nowrap">`revealjs`</span>
        ([reveal.js](http://lab.hakim.se/reveal-js/) HTML5 + JavaScript
        slide show)
    -   <span class="nowrap">`s5`</span>
        ([S5](http://meyerweb.com/eric/tools/s5/) HTML and JavaScript
        slide show)
    -   <span class="nowrap">`tei`</span> ([TEI
        Simple](https://github.com/TEIC/TEI-Simple))
    -   <span class="nowrap">`xwiki`</span> ([XWiki
        markup](https://www.xwiki.org/xwiki/bin/view/Documentation/UserGuide/Features/XWikiSyntax/))
    -   <span class="nowrap">`zimwiki`</span> ([ZimWiki
        markup](http://zim-wiki.org/manual/Help/Wiki_Syntax.html))
    -   the path of a custom lua writer, see [Custom
        writers](#custom-writers) below

    </div>

    Note that <span class="nowrap">`odt`</span>, <span
    class="nowrap">`docx`</span>, and <span class="nowrap">`epub`</span>
    output will not be directed to *stdout* unless forced with [<span
    class="nowrap">`-o -`</span>](#option--output){.option}.

    Extensions can be individually enabled or disabled by appending
    <span class="nowrap">`+EXTENSION`</span> or <span
    class="nowrap">`-EXTENSION`</span> to the format name. See
    [Extensions](#extensions) below, for a list of extensions and
    their names. See [<span
    class="nowrap">`--list-output-formats`</span>](#option--list-output-formats){.option}
    and [<span
    class="nowrap">`--list-extensions`</span>](#option--list-extensions){.option}, below.

<span id="option--output" class="option-anchor"><span class="nowrap">`-o`{.option-def}</span> *FILE*, <span class="nowrap">`--output=`{.option-def}</span>*FILE*</span>

:   Write output to *FILE* instead of *stdout*. If *FILE* is <span
    class="nowrap">`-`</span>, output will go to *stdout*, even if a
    non-textual format (<span class="nowrap">`docx`</span>, <span
    class="nowrap">`odt`</span>, <span class="nowrap">`epub2`</span>,
    <span class="nowrap">`epub3`</span>) is specified.

<span id="option--data-dir" class="option-anchor"><span class="nowrap">`--data-dir=`{.option-def}</span>*DIRECTORY*</span>

:   Specify the user data directory to search for pandoc data files. If
    this option is not specified, the default user data directory will
    be used. On \*nix and macOS systems this will be the <span
    class="nowrap">`pandoc`</span> subdirectory of the XDG data
    directory (by default, <span
    class="nowrap">`$HOME/.local/share`</span>, overridable by setting
    the <span class="nowrap">`XDG_DATA_HOME`</span>
    environment variable). If that directory does not exist, <span
    class="nowrap">`$HOME/.pandoc`</span> will be used (for
    backwards compatibility). In Windows the default user data directory
    is <span
    class="nowrap">`C:\Users\USERNAME\AppData\Roaming\pandoc`</span>.
    You can find the default user data directory on your system by
    looking at the output of <span
    class="nowrap">`pandoc --version`</span>. A <span
    class="nowrap">`reference.odt`</span>, <span
    class="nowrap">`reference.docx`</span>, <span
    class="nowrap">`epub.css`</span>, <span
    class="nowrap">`templates`</span>, <span
    class="nowrap">`slidy`</span>, <span
    class="nowrap">`slideous`</span>, or <span
    class="nowrap">`s5`</span> directory placed in this directory will
    override pandoc’s normal defaults.

<span id="option--bash-completion" class="option-anchor"><span class="nowrap">`--bash-completion`{.option-def}</span></span>

:   Generate a bash completion script. To enable bash completion with
    pandoc, add this to your <span class="nowrap">`.bashrc`</span>:

        eval "$(pandoc --bash-completion)"

<span id="option--verbose" class="option-anchor"><span class="nowrap">`--verbose`{.option-def}</span></span>

:   Give verbose debugging output. Currently this only has an effect
    with PDF output.

<span id="option--quiet" class="option-anchor"><span class="nowrap">`--quiet`{.option-def}</span></span>

:   Suppress warning messages.

<span id="option--fail-if-warnings" class="option-anchor"><span class="nowrap">`--fail-if-warnings`{.option-def}</span></span>

:   Exit with error status if there are any warnings.

<span id="option--log" class="option-anchor"><span class="nowrap">`--log=`{.option-def}</span>*FILE*</span>

:   Write log messages in machine-readable JSON format to *FILE*. All
    messages above DEBUG level will be written, regardless of verbosity
    settings ([<span
    class="nowrap">`--verbose`</span>](#option--verbose){.option},
    [<span class="nowrap">`--quiet`</span>](#option--quiet){.option}).

<span id="option--list-input-formats" class="option-anchor"><span class="nowrap">`--list-input-formats`{.option-def}</span></span>

:   List supported input formats, one per line.

<span id="option--list-output-formats" class="option-anchor"><span class="nowrap">`--list-output-formats`{.option-def}</span></span>

:   List supported output formats, one per line.

<span id="option--list-extensions" class="option-anchor"><span class="nowrap">`--list-extensions`{.option-def}</span>\[<span class="nowrap">`=`</span>*FORMAT*\]</span>

:   List supported extensions, one per line, preceded by a <span
    class="nowrap">`+`</span> or <span class="nowrap">`-`</span>
    indicating whether it is enabled by default in *FORMAT*. If *FORMAT*
    is not specified, defaults for pandoc’s Markdown are given.

<span id="option--list-highlight-languages" class="option-anchor"><span class="nowrap">`--list-highlight-languages`{.option-def}</span></span>

:   List supported languages for syntax highlighting, one per line.

<span id="option--list-highlight-styles" class="option-anchor"><span class="nowrap">`--list-highlight-styles`{.option-def}</span></span>

:   List supported styles for syntax highlighting, one per line. See
    [<span
    class="nowrap">`--highlight-style`</span>](#option--highlight-style){.option}.

<span id="option--version" class="option-anchor"><span class="nowrap">`-v`{.option-def}</span>, <span class="nowrap">`--version`{.option-def}</span></span>

:   Print version.

<span id="option--help" class="option-anchor"><span class="nowrap">`-h`{.option-def}</span>, <span class="nowrap">`--help`{.option-def}</span></span>

:   Show usage message.

Reader options {#reader-options .options}
--------------

<span id="option--base-header-level" class="option-anchor"><span class="nowrap">`--base-header-level=`{.option-def}</span>*NUMBER*</span>

:   Specify the base level for headings (defaults to 1).

<span id="option--strip-empty-paragraphs" class="option-anchor"><span class="nowrap">`--strip-empty-paragraphs`{.option-def}</span></span>

:   *Deprecated. Use the <span class="nowrap">`+empty_paragraphs`</span>
    extension instead.* Ignore paragraphs with no content. This option
    is useful for converting word processing documents where users have
    used empty paragraphs to create inter-paragraph space.

<span id="option--indented-code-classes" class="option-anchor"><span class="nowrap">`--indented-code-classes=`{.option-def}</span>*CLASSES*</span>

:   Specify classes to use for indented code blocks–for example, <span
    class="nowrap">`perl,numberLines`</span> or <span
    class="nowrap">`haskell`</span>. Multiple classes may be separated
    by spaces or commas.

<span id="option--default-image-extension" class="option-anchor"><span class="nowrap">`--default-image-extension=`{.option-def}</span>*EXTENSION*</span>

:   Specify a default extension to use when image paths/URLs have
    no extension. This allows you to use the same source for formats
    that require different kinds of images. Currently this option only
    affects the Markdown and LaTeX readers.

<span id="option--file-scope" class="option-anchor"><span class="nowrap">`--file-scope`{.option-def}</span></span>

:   Parse each file individually before combining for
    multifile documents. This will allow footnotes in different files
    with the same identifiers to work as expected. If this option is
    set, footnotes and links will not work across files. Reading binary
    files (docx, odt, epub) implies [<span
    class="nowrap">`--file-scope`</span>](#option--file-scope){.option}.

<span id="option--filter" class="option-anchor"><span class="nowrap">`-F`{.option-def}</span> *PROGRAM*, <span class="nowrap">`--filter=`{.option-def}</span>*PROGRAM*</span>

:   Specify an executable to be used as a filter transforming the pandoc
    AST after the input is parsed and before the output is written. The
    executable should read JSON from stdin and write JSON to stdout. The
    JSON must be formatted like pandoc’s own JSON input and output. The
    name of the output format will be passed to the filter as the
    first argument. Hence,

        pandoc --filter ./caps.py -t latex

    is equivalent to

        pandoc -t json | ./caps.py latex | pandoc -f json -t latex

    The latter form may be useful for debugging filters.

    Filters may be written in any language. <span
    class="nowrap">`Text.Pandoc.JSON`</span> exports <span
    class="nowrap">`toJSONFilter`</span> to facilitate writing filters
    in Haskell. Those who would prefer to write filters in python can
    use the module [<span
    class="nowrap">`pandocfilters`</span>](https://github.com/jgm/pandocfilters),
    installable from PyPI. There are also pandoc filter libraries in
    [PHP](https://github.com/vinai/pandocfilters-php),
    [perl](https://metacpan.org/pod/Pandoc::Filter), and
    [JavaScript/node.js](https://github.com/mvhenderson/pandoc-filter-node).

    In order of preference, pandoc will look for filters in

    1.  a specified full or relative path (executable or non-executable)

    2.  <span class="nowrap">`$DATADIR/filters`</span> (executable
        or non-executable) where <span class="nowrap">`$DATADIR`</span>
        is the user data directory (see [<span
        class="nowrap">`--data-dir`</span>](#option--data-dir){.option}, above).

    3.  <span class="nowrap">`$PATH`</span> (executable only)

    Filters and lua-filters are applied in the order specified on the
    command line.

<span id="option--lua-filter" class="option-anchor"><span class="nowrap">`--lua-filter=`{.option-def}</span>*SCRIPT*</span>

:   Transform the document in a similar fashion as JSON filters (see
    [<span class="nowrap">`--filter`</span>](#option--filter){.option}),
    but use pandoc’s build-in lua filtering system. The given lua script
    is expected to return a list of lua filters which will be applied
    in order. Each lua filter must contain element-transforming
    functions indexed by the name of the AST element on which the filter
    function should be applied.

    The <span class="nowrap">`pandoc`</span> lua module provides helper
    functions for element creation. It is always loaded into the
    script’s lua environment.

    The following is an example lua script for macro-expansion:

        function expand_hello_world(inline)
          if inline.c == '{{helloworld}}' then
            return pandoc.Emph{ pandoc.Str "Hello, World" }
          else
            return inline
          end
        end

        return {{Str = expand_hello_world}}

    In order of preference, pandoc will look for lua filters in

    1.  a specified full or relative path (executable or non-executable)

    2.  <span class="nowrap">`$DATADIR/filters`</span> (executable
        or non-executable) where <span class="nowrap">`$DATADIR`</span>
        is the user data directory (see [<span
        class="nowrap">`--data-dir`</span>](#option--data-dir){.option}, above).

<span id="option--metadata" class="option-anchor"><span class="nowrap">`-M`{.option-def}</span> *KEY*\[<span class="nowrap">`=`</span>*VAL*\], <span class="nowrap">`--metadata=`{.option-def}</span>*KEY*\[<span class="nowrap">`:`</span>*VAL*\]</span>

:   Set the metadata field *KEY* to the value *VAL*. A value specified
    on the command line overrides a value specified in the document
    using [YAML metadata blocks](#extension-yaml_metadata_block). Values
    will be parsed as YAML boolean or string values. If no value is
    specified, the value will be treated as Boolean true. Like [<span
    class="nowrap">`--variable`</span>](#option--variable){.option},
    [<span
    class="nowrap">`--metadata`</span>](#option--metadata){.option}
    causes template variables to be set. But unlike [<span
    class="nowrap">`--variable`</span>](#option--variable){.option},
    [<span
    class="nowrap">`--metadata`</span>](#option--metadata){.option}
    affects the metadata of the underlying document (which is accessible
    from filters and may be printed in some output formats) and metadata
    values will be escaped when inserted into the template.

<span id="option--metadata-file" class="option-anchor"><span class="nowrap">`--metadata-file=`{.option-def}</span>*FILE*</span>

:   Read metadata from the supplied YAML (or JSON) file. This option can
    be used with every input format, but string scalars in the YAML file
    will always be parsed as Markdown. Generally, the input will be
    handled the same as in [YAML metadata
    blocks](#extension-yaml_metadata_block). Metadata values specified
    inside the document, or by using [<span
    class="nowrap">`-M`</span>](#option--metadata){.option}, overwrite
    values specified with this option.

<span id="option--preserve-tabs" class="option-anchor"><span class="nowrap">`-p`{.option-def}</span>, <span class="nowrap">`--preserve-tabs`{.option-def}</span></span>

:   Preserve tabs instead of converting them to spaces (the default).
    Note that this will only affect tabs in literal code spans and code
    blocks; tabs in regular text will be treated as spaces.

<span id="option--tab-stop" class="option-anchor"><span class="nowrap">`--tab-stop=`{.option-def}</span>*NUMBER*</span>

:   Specify the number of spaces per tab (default is 4).

<span id="option--track-changes" class="option-anchor"><span class="nowrap">`--track-changes=accept`{.option-def}</span>|<span class="nowrap">`reject`</span>|<span class="nowrap">`all`</span></span>

:   Specifies what to do with insertions, deletions, and comments
    produced by the MS Word “Track Changes” feature. <span
    class="nowrap">`accept`</span> (the default), inserts all
    insertions, and ignores all deletions. <span
    class="nowrap">`reject`</span> inserts all deletions and
    ignores insertions. Both <span class="nowrap">`accept`</span> and
    <span class="nowrap">`reject`</span> ignore comments. <span
    class="nowrap">`all`</span> puts in insertions, deletions, and
    comments, wrapped in spans with <span
    class="nowrap">`insertion`</span>, <span
    class="nowrap">`deletion`</span>, <span
    class="nowrap">`comment-start`</span>, and <span
    class="nowrap">`comment-end`</span> classes, respectively. The
    author and time of change is included. <span
    class="nowrap">`all`</span> is useful for scripting: only accepting
    changes from a certain reviewer, say, or before a certain date. If a
    paragraph is inserted or deleted, <span
    class="nowrap">`track-changes=all`</span> produces a span with the
    class <span class="nowrap">`paragraph-insertion`</span>/<span
    class="nowrap">`paragraph-deletion`</span> before the affected
    paragraph break. This option only affects the docx reader.

<span id="option--extract-media" class="option-anchor"><span class="nowrap">`--extract-media=`{.option-def}</span>*DIR*</span>

:   Extract images and other media contained in or linked from the
    source document to the path *DIR*, creating it if necessary, and
    adjust the images references in the document so they point to the
    extracted files. If the source format is a binary container (docx,
    epub, or odt), the media is extracted from the container and the
    original filenames are used. Otherwise the media is read from the
    file system or downloaded, and new filenames are constructed based
    on SHA1 hashes of the contents.

<span id="option--abbreviations" class="option-anchor"><span class="nowrap">`--abbreviations=`{.option-def}</span>*FILE*</span>

:   Specifies a custom abbreviations file, with abbreviations one to
    a line. If this option is not specified, pandoc will read the data
    file <span class="nowrap">`abbreviations`</span> from the user data
    directory or fall back on a system default. To see the system
    default, use <span
    class="nowrap">`pandoc --print-default-data-file=abbreviations`</span>.
    The only use pandoc makes of this list is in the Markdown reader.
    Strings ending in a period that are found in this list will be
    followed by a nonbreaking space, so that the period will not produce
    sentence-ending space in formats like LaTeX.

General writer options {#general-writer-options .options}
----------------------

<span id="option--standalone" class="option-anchor"><span class="nowrap">`-s`{.option-def}</span>, <span class="nowrap">`--standalone`{.option-def}</span></span>

:   Produce output with an appropriate header and footer (e.g. a
    standalone HTML, LaTeX, TEI, or RTF file, not a fragment). This
    option is set automatically for <span class="nowrap">`pdf`</span>,
    <span class="nowrap">`epub`</span>, <span
    class="nowrap">`epub3`</span>, <span class="nowrap">`fb2`</span>,
    <span class="nowrap">`docx`</span>, and <span
    class="nowrap">`odt`</span> output. For <span
    class="nowrap">`native`</span> output, this option causes metadata
    to be included; otherwise, metadata is suppressed.

<span id="option--template" class="option-anchor"><span class="nowrap">`--template=`{.option-def}</span>*FILE*|*URL*</span>

:   Use the specified file as a custom template for the
    generated document. Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.
    See [Templates](#templates), below, for a description of
    template syntax. If no extension is specified, an extension
    corresponding to the writer will be added, so that [<span
    class="nowrap">`--template=special`</span>](#option--template){.option}
    looks for <span class="nowrap">`special.html`</span> for
    HTML output. If the template is not found, pandoc will search for it
    in the <span class="nowrap">`templates`</span> subdirectory of the
    user data directory (see [<span
    class="nowrap">`--data-dir`</span>](#option--data-dir){.option}). If
    this option is not used, a default template appropriate for the
    output format will be used (see [<span
    class="nowrap">`-D/--print-default-template`</span>](#option--print-default-template){.option}).

<span id="option--variable" class="option-anchor"><span class="nowrap">`-V`{.option-def}</span> *KEY*\[<span class="nowrap">`=`</span>*VAL*\], <span class="nowrap">`--variable=`{.option-def}</span>*KEY*\[<span class="nowrap">`:`</span>*VAL*\]</span>

:   Set the template variable *KEY* to the value *VAL* when rendering
    the document in standalone mode. This is generally only useful when
    the [<span
    class="nowrap">`--template`</span>](#option--template){.option}
    option is used to specify a custom template, since pandoc
    automatically sets the variables used in the default templates. If
    no *VAL* is specified, the key will be given the value <span
    class="nowrap">`true`</span>.

<span id="option--print-default-template" class="option-anchor"><span class="nowrap">`-D`{.option-def}</span> *FORMAT*, <span class="nowrap">`--print-default-template=`{.option-def}</span>*FORMAT*</span>

:   Print the system default template for an output *FORMAT*. (See
    [<span class="nowrap">`-t`</span>](#option--to){.option} for a list
    of possible *FORMAT*s.) Templates in the user data directory
    are ignored. This option may be used with [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} to
    redirect output to a file, but [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} must
    come before [<span
    class="nowrap">`--print-default-template`</span>](#option--print-default-template){.option}
    on the command line.

<span id="option--print-default-data-file" class="option-anchor"><span class="nowrap">`--print-default-data-file=`{.option-def}</span>*FILE*</span>

:   Print a system default data file. Files in the user data directory
    are ignored. This option may be used with [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} to
    redirect output to a file, but [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} must
    come before [<span
    class="nowrap">`--print-default-data-file`</span>](#option--print-default-data-file){.option}
    on the command line.

<span id="option--eol" class="option-anchor"><span class="nowrap">`--eol=crlf`{.option-def}</span>|<span class="nowrap">`lf`</span>|<span class="nowrap">`native`</span></span>

:   Manually specify line endings: <span class="nowrap">`crlf`</span>
    (Windows), <span class="nowrap">`lf`</span> (macOS/Linux/UNIX), or
    <span class="nowrap">`native`</span> (line endings appropriate to
    the OS on which pandoc is being run). The default is <span
    class="nowrap">`native`</span>.

<span id="option--dpi" class="option-anchor"><span class="nowrap">`--dpi`{.option-def}</span>=*NUMBER*</span>

:   Specify the dpi (dots per inch) value for conversion from pixels to
    inch/centimeters and vice versa. The default is 96dpi. Technically,
    the correct term would be ppi (pixels per inch).

<span id="option--wrap" class="option-anchor"><span class="nowrap">`--wrap=auto`{.option-def}</span>|<span class="nowrap">`none`</span>|<span class="nowrap">`preserve`</span></span>

:   Determine how text is wrapped in the output (the source code, not
    the rendered version). With <span class="nowrap">`auto`</span> (the
    default), pandoc will attempt to wrap lines to the column width
    specified by [<span
    class="nowrap">`--columns`</span>](#option--columns){.option}
    (default 72). With <span class="nowrap">`none`</span>, pandoc will
    not wrap lines at all. With <span class="nowrap">`preserve`</span>,
    pandoc will attempt to preserve the wrapping from the source
    document (that is, where there are nonsemantic newlines in the
    source, there will be nonsemantic newlines in the output as well).
    Automatic wrapping does not currently work in HTML output. In <span
    class="nowrap">`ipynb`</span> output, this option affects wrapping
    of the contents of markdown cells.

<span id="option--columns" class="option-anchor"><span class="nowrap">`--columns=`{.option-def}</span>*NUMBER*</span>

:   Specify length of lines in characters. This affects text wrapping in
    the generated source code (see [<span
    class="nowrap">`--wrap`</span>](#option--wrap){.option}). It also
    affects calculation of column widths for plain text tables (see
    [Tables](#tables) below).

<span id="option--toc" class="option-anchor"><span class="nowrap">`--toc`{.option-def}</span>, <span class="nowrap">`--table-of-contents`{.option-def}</span></span>

:   Include an automatically generated table of contents (or, in the
    case of <span class="nowrap">`latex`</span>, <span
    class="nowrap">`context`</span>, <span class="nowrap">`docx`</span>,
    <span class="nowrap">`odt`</span>, <span
    class="nowrap">`opendocument`</span>, <span
    class="nowrap">`rst`</span>, or <span class="nowrap">`ms`</span>, an
    instruction to create one) in the output document. This option has
    no effect unless [<span
    class="nowrap">`-s/--standalone`</span>](#option--standalone){.option}
    is used, and it has no effect on <span class="nowrap">`man`</span>,
    <span class="nowrap">`docbook4`</span>, <span
    class="nowrap">`docbook5`</span>, or <span
    class="nowrap">`jats`</span> output.

    Note that if you are producing a PDF via <span
    class="nowrap">`ms`</span>, the table of contents will appear at the
    beginning of the document, before the title. If you would prefer it
    to be at the end of the document, use the option [<span
    class="nowrap">`--pdf-engine-opt=--no-toc-relocation`</span>](#option--pdf-engine-opt){.option}.

<span id="option--toc-depth" class="option-anchor"><span class="nowrap">`--toc-depth=`{.option-def}</span>*NUMBER*</span>

:   Specify the number of section levels to include in the table
    of contents. The default is 3 (which means that level-1, 2, and 3
    headings will be listed in the contents).

<span id="option--strip-comments" class="option-anchor"><span class="nowrap">`--strip-comments`{.option-def}</span></span>

:   Strip out HTML comments in the Markdown or Textile source, rather
    than passing them on to Markdown, Textile or HTML output as
    raw HTML. This does not apply to HTML comments inside raw HTML
    blocks when the <span
    class="nowrap">`markdown_in_html_blocks`</span> extension is
    not set.

<span id="option--no-highlight" class="option-anchor"><span class="nowrap">`--no-highlight`{.option-def}</span></span>

:   Disables syntax highlighting for code blocks and inlines, even when
    a language attribute is given.

<span id="option--highlight-style" class="option-anchor"><span class="nowrap">`--highlight-style=`{.option-def}</span>*STYLE*|*FILE*</span>

:   Specifies the coloring style to be used in highlighted source code.
    Options are <span class="nowrap">`pygments`</span> (the default),
    <span class="nowrap">`kate`</span>, <span
    class="nowrap">`monochrome`</span>, <span
    class="nowrap">`breezeDark`</span>, <span
    class="nowrap">`espresso`</span>, <span
    class="nowrap">`zenburn`</span>, <span
    class="nowrap">`haddock`</span>, and <span
    class="nowrap">`tango`</span>. For more information on syntax
    highlighting in pandoc, see [Syntax
    highlighting](#syntax-highlighting), below. See also [<span
    class="nowrap">`--list-highlight-styles`</span>](#option--list-highlight-styles){.option}.

    Instead of a *STYLE* name, a JSON file with extension <span
    class="nowrap">`.theme`</span> may be supplied. This will be parsed
    as a KDE syntax highlighting theme and (if valid) used as the
    highlighting style.

    To generate the JSON version of an existing style, use [<span
    class="nowrap">`--print-highlight-style`</span>](#option--print-highlight-style){.option}.

<span id="option--print-highlight-style" class="option-anchor"><span class="nowrap">`--print-highlight-style=`{.option-def}</span>*STYLE*|*FILE*</span>

:   Prints a JSON version of a highlighting style, which can be
    modified, saved with a <span class="nowrap">`.theme`</span>
    extension, and used with [<span
    class="nowrap">`--highlight-style`</span>](#option--highlight-style){.option}.
    This option may be used with [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} to
    redirect output to a file, but [<span
    class="nowrap">`-o`</span>](#option--output){.option}/[<span
    class="nowrap">`--output`</span>](#option--output){.option} must
    come before [<span
    class="nowrap">`--print-highlight-style`</span>](#option--print-highlight-style){.option}
    on the command line.

<span id="option--syntax-definition" class="option-anchor"><span class="nowrap">`--syntax-definition=`{.option-def}</span>*FILE*</span>

:   Instructs pandoc to load a KDE XML syntax definition file, which
    will be used for syntax highlighting of appropriately marked
    code blocks. This can be used to add support for new languages or to
    use altered syntax definitions for existing languages.

<span id="option--include-in-header" class="option-anchor"><span class="nowrap">`-H`{.option-def}</span> *FILE*, <span class="nowrap">`--include-in-header=`{.option-def}</span>*FILE*|*URL*</span>

:   Include contents of *FILE*, verbatim, at the end of the header. This
    can be used, for example, to include special CSS or JavaScript in
    HTML documents. This option can be used repeatedly to include
    multiple files in the header. They will be included in the
    order specified. Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.

<span id="option--include-before-body" class="option-anchor"><span class="nowrap">`-B`{.option-def}</span> *FILE*, <span class="nowrap">`--include-before-body=`{.option-def}</span>*FILE*|*URL*</span>

:   Include contents of *FILE*, verbatim, at the beginning of the
    document body (e.g. after the <span class="nowrap">`<body>`</span>
    tag in HTML, or the <span class="nowrap">`\begin{document}`</span>
    command in LaTeX). This can be used to include navigation bars or
    banners in HTML documents. This option can be used repeatedly to
    include multiple files. They will be included in the
    order specified. Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.

<span id="option--include-after-body" class="option-anchor"><span class="nowrap">`-A`{.option-def}</span> *FILE*, <span class="nowrap">`--include-after-body=`{.option-def}</span>*FILE*|*URL*</span>

:   Include contents of *FILE*, verbatim, at the end of the document
    body (before the <span class="nowrap">`</body>`</span> tag in HTML,
    or the <span class="nowrap">`\end{document}`</span> command
    in LaTeX). This option can be used repeatedly to include
    multiple files. They will be included in the order specified.
    Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.

<span id="option--resource-path" class="option-anchor"><span class="nowrap">`--resource-path=`{.option-def}</span>*SEARCHPATH*</span>

:   List of paths to search for images and other resources. The paths
    should be separated by <span class="nowrap">`:`</span> on Linux,
    UNIX, and macOS systems, and by <span class="nowrap">`;`</span>
    on Windows. If [<span
    class="nowrap">`--resource-path`</span>](#option--resource-path){.option}
    is not specified, the default resource path is the
    working directory. Note that, if [<span
    class="nowrap">`--resource-path`</span>](#option--resource-path){.option}
    is specified, the working directory must be explicitly listed or it
    will not be searched. For example: [<span
    class="nowrap">`--resource-path=.:test`</span>](#option--resource-path){.option}
    will search the working directory and the <span
    class="nowrap">`test`</span> subdirectory, in that order.

    [<span
    class="nowrap">`--resource-path`</span>](#option--resource-path){.option}
    only has an effect if (a) the output format embeds images (for
    example, <span class="nowrap">`docx`</span>, <span
    class="nowrap">`pdf`</span>, or <span class="nowrap">`html`</span>
    with [<span
    class="nowrap">`--self-contained`</span>](#option--self-contained){.option})
    or (b) it is used together with [<span
    class="nowrap">`--extract-media`</span>](#option--extract-media){.option}.

<span id="option--request-header" class="option-anchor"><span class="nowrap">`--request-header=`{.option-def}</span>*NAME*<span class="nowrap">`:`</span>*VAL*</span>

:   Set the request header *NAME* to the value *VAL* when making HTTP
    requests (for example, when a URL is given on the command line, or
    when resources used in a document must be downloaded). If you’re
    behind a proxy, you also need to set the environment variable <span
    class="nowrap">`http_proxy`</span> to <span
    class="nowrap">`http://...`</span>.

Options affecting specific writers {#options-affecting-specific-writers .options}
----------------------------------

<span id="option--self-contained" class="option-anchor"><span class="nowrap">`--self-contained`{.option-def}</span></span>

:   Produce a standalone HTML file with no external dependencies, using
    <span class="nowrap">`data:`</span> URIs to incorporate the contents
    of linked scripts, stylesheets, images, and videos. Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.
    The resulting file should be “self-contained,” in the sense that it
    needs no external files and no net access to be displayed properly
    by a browser. This option works only with HTML output formats,
    including <span class="nowrap">`html4`</span>, <span
    class="nowrap">`html5`</span>, <span
    class="nowrap">`html+lhs`</span>, <span
    class="nowrap">`html5+lhs`</span>, <span class="nowrap">`s5`</span>,
    <span class="nowrap">`slidy`</span>, <span
    class="nowrap">`slideous`</span>, <span
    class="nowrap">`dzslides`</span>, and <span
    class="nowrap">`revealjs`</span>. Scripts, images, and stylesheets
    at absolute URLs will be downloaded; those at relative URLs will be
    sought relative to the working directory (if the first source file
    is local) or relative to the base URL (if the first source file
    is remote). Elements with the attribute <span
    class="nowrap">`data-external="1"`</span> will be left alone; the
    documents they link to will not be incorporated in the document.
    Limitation: resources that are loaded dynamically through JavaScript
    cannot be incorporated; as a result, [<span
    class="nowrap">`--self-contained`</span>](#option--self-contained){.option}
    does not work with [<span
    class="nowrap">`--mathjax`</span>](#option--mathjax){.option}, and
    some advanced features (e.g. zoom or speaker notes) may not work in
    an offline “self-contained” <span class="nowrap">`reveal.js`</span>
    slide show.

<span id="option--html-q-tags" class="option-anchor"><span class="nowrap">`--html-q-tags`{.option-def}</span></span>

:   Use <span class="nowrap">`<q>`</span> tags for quotes in HTML.

<span id="option--ascii" class="option-anchor"><span class="nowrap">`--ascii`{.option-def}</span></span>

:   Use only ASCII characters in output. Currently supported for XML and
    HTML formats (which use entities instead of UTF-8 when this option
    is selected), CommonMark, gfm, and Markdown (which use entities),
    roff ms (which use hexadecimal escapes), and to a limited degree
    LaTeX (which uses standard commands for accented characters
    when possible). roff man output uses ASCII by default.

<span id="option--reference-links" class="option-anchor"><span class="nowrap">`--reference-links`{.option-def}</span></span>

:   Use reference-style links, rather than inline links, in writing
    Markdown or reStructuredText. By default inline links are used. The
    placement of link references is affected by the [<span
    class="nowrap">`--reference-location`</span>](#option--reference-location%20){.option} option.

<span id="option--reference-location " class="option-anchor"><span class="nowrap">`--reference-location = block`{.option-def}</span>|<span class="nowrap">`section`</span>|<span class="nowrap">`document`</span></span>

:   Specify whether footnotes (and references, if <span
    class="nowrap">`reference-links`</span> is set) are placed at the
    end of the current (top-level) block, the current section, or
    the document. The default is <span class="nowrap">`document`</span>.
    Currently only affects the markdown writer.

<span id="option--atx-headers" class="option-anchor"><span class="nowrap">`--atx-headers`{.option-def}</span></span>

:   Use ATX-style headings in Markdown output. The default is to use
    setext-style headings for levels 1 to 2, and then ATX headings.
    (Note: for <span class="nowrap">`gfm`</span> output, ATX headings
    are always used.) This option also affects markdown cells in <span
    class="nowrap">`ipynb`</span> output.

<span id="option--top-level-division" class="option-anchor"><span class="nowrap">`--top-level-division=[default|section|chapter|part]`{.option-def}</span></span>

:   Treat top-level headings as the given division type in LaTeX,
    ConTeXt, DocBook, and TEI output. The hierarchy order is part,
    chapter, then section; all headings are shifted such that the
    top-level heading becomes the specified type. The default behavior
    is to determine the best division type via heuristics: unless other
    conditions apply, <span class="nowrap">`section`</span> is chosen.
    When the LaTeX document class is set to <span
    class="nowrap">`report`</span>, <span class="nowrap">`book`</span>,
    or <span class="nowrap">`memoir`</span> (unless the <span
    class="nowrap">`article`</span> option is specified), <span
    class="nowrap">`chapter`</span> is implied as the setting for
    this option. If <span class="nowrap">`beamer`</span> is the output
    format, specifying either <span class="nowrap">`chapter`</span> or
    <span class="nowrap">`part`</span> will cause top-level headings to
    become <span class="nowrap">`\part{..}`</span>, while second-level
    headings remain as their default type.

<span id="option--number-sections" class="option-anchor"><span class="nowrap">`-N`{.option-def}</span>, <span class="nowrap">`--number-sections`{.option-def}</span></span>

:   Number section headings in LaTeX, ConTeXt, HTML, or EPUB output. By
    default, sections are not numbered. Sections with class <span
    class="nowrap">`unnumbered`</span> will never be numbered, even if
    [<span
    class="nowrap">`--number-sections`</span>](#option--number-sections){.option}
    is specified.

<span id="option--number-offset" class="option-anchor"><span class="nowrap">`--number-offset=`{.option-def}</span>*NUMBER*\[<span class="nowrap">`,`</span>*NUMBER*<span class="nowrap">`,`</span>*…*\]</span>

:   Offset for section headings in HTML output (ignored in other
    output formats). The first number is added to the section number for
    top-level headings, the second for second-level headings, and so on.
    So, for example, if you want the first top-level heading in your
    document to be numbered “6”, specify [<span
    class="nowrap">`--number-offset=5`</span>](#option--number-offset){.option}.
    If your document starts with a level-2 heading which you want to be
    numbered “1.5”, specify [<span
    class="nowrap">`--number-offset=1,4`</span>](#option--number-offset){.option}.
    Offsets are 0 by default. Implies [<span
    class="nowrap">`--number-sections`</span>](#option--number-sections){.option}.

<span id="option--listings" class="option-anchor"><span class="nowrap">`--listings`{.option-def}</span></span>

:   Use the [<span
    class="nowrap">`listings`</span>](https://ctan.org/pkg/listings)
    package for LaTeX code blocks. The package does not support
    multi-byte encoding for source code. To handle UTF-8 you would need
    to use a custom template. This issue is fully documented here:
    [Encoding issue with the listings
    package](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings#Encoding_issue).

<span id="option--incremental" class="option-anchor"><span class="nowrap">`-i`{.option-def}</span>, <span class="nowrap">`--incremental`{.option-def}</span></span>

:   Make list items in slide shows display incrementally (one by one).
    The default is for lists to be displayed all at once.

<span id="option--slide-level" class="option-anchor"><span class="nowrap">`--slide-level=`{.option-def}</span>*NUMBER*</span>

:   Specifies that headings with the specified level create slides (for
    <span class="nowrap">`beamer`</span>, <span
    class="nowrap">`s5`</span>, <span class="nowrap">`slidy`</span>,
    <span class="nowrap">`slideous`</span>, <span
    class="nowrap">`dzslides`</span>). Headings above this level in the
    hierarchy are used to divide the slide show into sections; headings
    below this level create subheads within a slide. Note that content
    that is not contained under slide-level headings will not appear in
    the slide show. The default is to set the slide level based on the
    contents of the document; see [Structuring the slide
    show](#structuring-the-slide-show).

<span id="option--section-divs" class="option-anchor"><span class="nowrap">`--section-divs`{.option-def}</span></span>

:   Wrap sections in <span class="nowrap">`<section>`</span> tags (or
    <span class="nowrap">`<div>`</span> tags for <span
    class="nowrap">`html4`</span>), and attach identifiers to the
    enclosing <span class="nowrap">`<section>`</span> (or <span
    class="nowrap">`<div>`</span>) rather than the heading itself. See
    [Heading identifiers](#heading-identifiers), below.

<span id="option--email-obfuscation" class="option-anchor"><span class="nowrap">`--email-obfuscation=none`{.option-def}</span>|<span class="nowrap">`javascript`</span>|<span class="nowrap">`references`</span></span>

:   Specify a method for obfuscating <span
    class="nowrap">`mailto:`</span> links in HTML documents. <span
    class="nowrap">`none`</span> leaves <span
    class="nowrap">`mailto:`</span> links as they are. <span
    class="nowrap">`javascript`</span> obfuscates them using JavaScript.
    <span class="nowrap">`references`</span> obfuscates them by printing
    their letters as decimal or hexadecimal character references. The
    default is <span class="nowrap">`none`</span>.

<span id="option--id-prefix" class="option-anchor"><span class="nowrap">`--id-prefix=`{.option-def}</span>*STRING*</span>

:   Specify a prefix to be added to all identifiers and internal links
    in HTML and DocBook output, and to footnote numbers in Markdown and
    Haddock output. This is useful for preventing duplicate identifiers
    when generating fragments to be included in other pages.

<span id="option--title-prefix" class="option-anchor"><span class="nowrap">`-T`{.option-def}</span> *STRING*, <span class="nowrap">`--title-prefix=`{.option-def}</span>*STRING*</span>

:   Specify *STRING* as a prefix at the beginning of the title that
    appears in the HTML header (but not in the title as it appears at
    the beginning of the HTML body). Implies [<span
    class="nowrap">`--standalone`</span>](#option--standalone){.option}.

<span id="option--css" class="option-anchor"><span class="nowrap">`-c`{.option-def}</span> *URL*, <span class="nowrap">`--css=`{.option-def}</span>*URL*</span>

:   Link to a CSS style sheet. This option can be used repeatedly to
    include multiple files. They will be included in the
    order specified.

    A stylesheet is required for generating EPUB. If none is provided
    using this option (or the <span class="nowrap">`css`</span> or <span
    class="nowrap">`stylesheet`</span> metadata fields), pandoc will
    look for a file <span class="nowrap">`epub.css`</span> in the user
    data directory (see [<span
    class="nowrap">`--data-dir`</span>](#option--data-dir){.option}). If
    it is not found there, sensible defaults will be used.

<span id="option--reference-doc" class="option-anchor"><span class="nowrap">`--reference-doc=`{.option-def}</span>*FILE*</span>

:   Use the specified file as a style reference in producing a docx or
    ODT file.

    Docx

    :   For best results, the reference docx should be a modified
        version of a docx file produced using pandoc. The contents of
        the reference docx are ignored, but its stylesheets and document
        properties (including margins, page size, header, and footer)
        are used in the new docx. If no reference docx is specified on
        the command line, pandoc will look for a file <span
        class="nowrap">`reference.docx`</span> in the user data
        directory (see [<span
        class="nowrap">`--data-dir`</span>](#option--data-dir){.option}).
        If this is not found either, sensible defaults will be used.

        To produce a custom <span
        class="nowrap">`reference.docx`</span>, first get a copy of the
        default <span class="nowrap">`reference.docx`</span>: <span
        class="nowrap">`pandoc -o custom-reference.docx --print-default-data-file reference.docx`</span>.
        Then open <span class="nowrap">`custom-reference.docx`</span> in
        Word, modify the styles as you wish, and save the file. For best
        results, do not make changes to this file other than modifying
        the styles used by pandoc:

        Paragraph styles:

        -   Normal
        -   Body Text
        -   First Paragraph
        -   Compact
        -   Title
        -   Subtitle
        -   Author
        -   Date
        -   Abstract
        -   Bibliography
        -   Heading 1
        -   Heading 2
        -   Heading 3
        -   Heading 4
        -   Heading 5
        -   Heading 6
        -   Heading 7
        -   Heading 8
        -   Heading 9
        -   Block Text
        -   Footnote Text
        -   Definition Term
        -   Definition
        -   Caption
        -   Table Caption
        -   Image Caption
        -   Figure
        -   Captioned Figure
        -   TOC Heading

        Character styles:

        -   Default Paragraph Font
        -   Body Text Char
        -   Verbatim Char
        -   Footnote Reference
        -   Hyperlink

        Table style:

        -   Table

    ODT

    :   For best results, the reference ODT should be a modified version
        of an ODT produced using pandoc. The contents of the reference
        ODT are ignored, but its stylesheets are used in the new ODT. If
        no reference ODT is specified on the command line, pandoc will
        look for a file <span class="nowrap">`reference.odt`</span> in
        the user data directory (see [<span
        class="nowrap">`--data-dir`</span>](#option--data-dir){.option}).
        If this is not found either, sensible defaults will be used.

        To produce a custom <span class="nowrap">`reference.odt`</span>,
        first get a copy of the default <span
        class="nowrap">`reference.odt`</span>: <span
        class="nowrap">`pandoc -o custom-reference.odt --print-default-data-file reference.odt`</span>.
        Then open <span class="nowrap">`custom-reference.odt`</span> in
        LibreOffice, modify the styles as you wish, and save the file.

    PowerPoint

    :   Templates included with Microsoft PowerPoint 2013 (either with
        <span class="nowrap">`.pptx`</span> or <span
        class="nowrap">`.potx`</span> extension) are known to work, as
        are most templates derived from these.

        The specific requirement is that the template should begin with
        the following first four layouts:

        1.  Title Slide
        2.  Title and Content
        3.  Section Header
        4.  Two Content

        All templates included with a recent version of MS PowerPoint
        will fit these criteria. (You can click on <span
        class="nowrap">`Layout`</span> under the <span
        class="nowrap">`Home`</span> menu to check.)

        You can also modify the default <span
        class="nowrap">`reference.pptx`</span>: first run <span
        class="nowrap">`pandoc -o custom-reference.pptx --print-default-data-file reference.pptx`</span>,
        and then modify <span
        class="nowrap">`custom-reference.pptx`</span> in MS PowerPoint
        (pandoc will use the first four layout slides, as
        mentioned above).

<span id="option--epub-cover-image" class="option-anchor"><span class="nowrap">`--epub-cover-image=`{.option-def}</span>*FILE*</span>

:   Use the specified image as the EPUB cover. It is recommended that
    the image be less than 1000px in width and height. Note that in a
    Markdown source document you can also specify <span
    class="nowrap">`cover-image`</span> in a YAML metadata block (see
    [EPUB Metadata](#epub-metadata), below).

<span id="option--epub-metadata" class="option-anchor"><span class="nowrap">`--epub-metadata=`{.option-def}</span>*FILE*</span>

:   Look in the specified XML file for metadata for the EPUB. The file
    should contain a series of [Dublin Core
    elements](http://dublincore.org/documents/dces/). For example:

         <dc:rights>Creative Commons</dc:rights>
         <dc:language>es-AR</dc:language>

    By default, pandoc will include the following metadata elements:
    <span class="nowrap">`<dc:title>`</span> (from the document title),
    <span class="nowrap">`<dc:creator>`</span> (from the document
    authors), <span class="nowrap">`<dc:date>`</span> (from the document
    date, which should be in [ISO 8601
    format](http://www.w3.org/TR/NOTE-datetime)), <span
    class="nowrap">`<dc:language>`</span> (from the <span
    class="nowrap">`lang`</span> variable, or, if is not set, the
    locale), and <span
    class="nowrap">`<dc:identifier id="BookId">`</span> (a randomly
    generated UUID). Any of these may be overridden by elements in the
    metadata file.

    Note: if the source document is Markdown, a YAML metadata block in
    the document can be used instead. See below under [EPUB
    Metadata](#epub-metadata).

<span id="option--epub-embed-font" class="option-anchor"><span class="nowrap">`--epub-embed-font=`{.option-def}</span>*FILE*</span>

:   Embed the specified font in the EPUB. This option can be repeated to
    embed multiple fonts. Wildcards can also be used: for example, <span
    class="nowrap">`DejaVuSans-*.ttf`</span>. However, if you use
    wildcards on the command line, be sure to escape them or put the
    whole filename in single quotes, to prevent them from being
    interpreted by the shell. To use the embedded fonts, you will need
    to add declarations like the following to your CSS (see [<span
    class="nowrap">`--css`</span>](#option--css){.option}):

        @font-face {
        font-family: DejaVuSans;
        font-style: normal;
        font-weight: normal;
        src:url("DejaVuSans-Regular.ttf");
        }
        @font-face {
        font-family: DejaVuSans;
        font-style: normal;
        font-weight: bold;
        src:url("DejaVuSans-Bold.ttf");
        }
        @font-face {
        font-family: DejaVuSans;
        font-style: italic;
        font-weight: normal;
        src:url("DejaVuSans-Oblique.ttf");
        }
        @font-face {
        font-family: DejaVuSans;
        font-style: italic;
        font-weight: bold;
        src:url("DejaVuSans-BoldOblique.ttf");
        }
        body { font-family: "DejaVuSans"; }

<span id="option--epub-chapter-level" class="option-anchor"><span class="nowrap">`--epub-chapter-level=`{.option-def}</span>*NUMBER*</span>

:   Specify the heading level at which to split the EPUB into separate
    “chapter” files. The default is to split into chapters at
    level-1 headings. This option only affects the internal composition
    of the EPUB, not the way chapters and sections are displayed
    to users. Some readers may be slow if the chapter files are too
    large, so for large documents with few level-1 headings, one might
    want to use a chapter level of 2 or 3.

<span id="option--epub-subdirectory" class="option-anchor"><span class="nowrap">`--epub-subdirectory=`{.option-def}</span>*DIRNAME*</span>

:   Specify the subdirectory in the OCF container that is to hold the
    EPUB-specific contents. The default is <span
    class="nowrap">`EPUB`</span>. To put the EPUB contents in the top
    level, use an empty string.

<span id="option--ipynb-output" class="option-anchor"><span class="nowrap">`--ipynb-output=all|none|best`{.option-def}</span></span>

:   Determines how ipynb output cells are treated. <span
    class="nowrap">`all`</span> means that all of the data formats
    included in the original are preserved. <span
    class="nowrap">`none`</span> means that the contents of data cells
    are omitted. <span class="nowrap">`best`</span> causes pandoc to try
    to pick the richest data block in each output cell that is
    compatible with the output format. The default is <span
    class="nowrap">`best`</span>.

<span id="option--pdf-engine" class="option-anchor"><span class="nowrap">`--pdf-engine=`{.option-def}</span>*PROGRAM*</span>

:   Use the specified engine when producing PDF output. Valid values are
    <span class="nowrap">`pdflatex`</span>, <span
    class="nowrap">`lualatex`</span>, <span
    class="nowrap">`xelatex`</span>, <span
    class="nowrap">`latexmk`</span>, <span
    class="nowrap">`tectonic`</span>, <span
    class="nowrap">`wkhtmltopdf`</span>, <span
    class="nowrap">`weasyprint`</span>, <span
    class="nowrap">`prince`</span>, <span
    class="nowrap">`context`</span>, and <span
    class="nowrap">`pdfroff`</span>. The default is <span
    class="nowrap">`pdflatex`</span>. If the engine is not in your PATH,
    the full path of the engine may be specified here.

<span id="option--pdf-engine-opt" class="option-anchor"><span class="nowrap">`--pdf-engine-opt=`{.option-def}</span>*STRING*</span>

:   Use the given string as a command-line argument to the <span
    class="nowrap">`pdf-engine`</span>. For example, to use a persistent
    directory <span class="nowrap">`foo`</span> for <span
    class="nowrap">`latexmk`</span>’s auxiliary files, use [<span
    class="nowrap">`--pdf-engine-opt=-outdir=foo`</span>](#option--pdf-engine-opt){.option}.
    Note that no check for duplicate options is done.

Citation rendering {#citation-rendering .options}
------------------

<span id="option--bibliography" class="option-anchor"><span class="nowrap">`--bibliography=`{.option-def}</span>*FILE*</span>

:   Set the <span class="nowrap">`bibliography`</span> field in the
    document’s metadata to *FILE*, overriding any value set in the
    metadata, and process citations using <span
    class="nowrap">`pandoc-citeproc`</span>. (This is equivalent to
    [<span
    class="nowrap">`--metadata bibliography=FILE --filter pandoc-citeproc`</span>](#option--metadata){.option}.)
    If [<span
    class="nowrap">`--natbib`</span>](#option--natbib){.option} or
    [<span
    class="nowrap">`--biblatex`</span>](#option--biblatex){.option} is
    also supplied, <span class="nowrap">`pandoc-citeproc`</span> is not
    used, making this equivalent to [<span
    class="nowrap">`--metadata bibliography=FILE`</span>](#option--metadata){.option}.
    If you supply this argument multiple times, each *FILE* will be
    added to bibliography.

<span id="option--csl" class="option-anchor"><span class="nowrap">`--csl=`{.option-def}</span>*FILE*</span>

:   Set the <span class="nowrap">`csl`</span> field in the document’s
    metadata to *FILE*, overriding any value set in the metadata. (This
    is equivalent to [<span
    class="nowrap">`--metadata csl=FILE`</span>](#option--metadata){.option}.)
    This option is only relevant with <span
    class="nowrap">`pandoc-citeproc`</span>.

<span id="option--citation-abbreviations" class="option-anchor"><span class="nowrap">`--citation-abbreviations=`{.option-def}</span>*FILE*</span>

:   Set the <span class="nowrap">`citation-abbreviations`</span> field
    in the document’s metadata to *FILE*, overriding any value set in
    the metadata. (This is equivalent to [<span
    class="nowrap">`--metadata citation-abbreviations=FILE`</span>](#option--metadata){.option}.)
    This option is only relevant with <span
    class="nowrap">`pandoc-citeproc`</span>.

<span id="option--natbib" class="option-anchor"><span class="nowrap">`--natbib`{.option-def}</span></span>

:   Use [<span
    class="nowrap">`natbib`</span>](https://ctan.org/pkg/natbib) for
    citations in LaTeX output. This option is not for use with the <span
    class="nowrap">`pandoc-citeproc`</span> filter or with PDF output.
    It is intended for use in producing a LaTeX file that can be
    processed with [<span
    class="nowrap">`bibtex`</span>](https://ctan.org/pkg/bibtex).

<span id="option--biblatex" class="option-anchor"><span class="nowrap">`--biblatex`{.option-def}</span></span>

:   Use [<span
    class="nowrap">`biblatex`</span>](https://ctan.org/pkg/biblatex) for
    citations in LaTeX output. This option is not for use with the <span
    class="nowrap">`pandoc-citeproc`</span> filter or with PDF output.
    It is intended for use in producing a LaTeX file that can be
    processed with [<span
    class="nowrap">`bibtex`</span>](https://ctan.org/pkg/bibtex) or
    [<span class="nowrap">`biber`</span>](https://ctan.org/pkg/biber).

Math rendering in HTML {#math-rendering-in-html .options}
----------------------

The default is to render TeX math as far as possible using Unicode
characters. Formulas are put inside a <span class="nowrap">`span`</span>
with <span class="nowrap">`class="math"`</span>, so that they may be
styled differently from the surrounding text if needed. However, this
gives acceptable results only for basic math, usually you will want to
use [<span class="nowrap">`--mathjax`</span>](#option--mathjax){.option}
or another of the following options.

<span id="option--mathjax" class="option-anchor"><span class="nowrap">`--mathjax`{.option-def}</span>\[<span class="nowrap">`=`</span>*URL*\]</span>

:   Use [MathJax](https://www.mathjax.org) to display embedded TeX math
    in HTML output. TeX math will be put between <span
    class="nowrap">`\(...\)`</span> (for inline math) or <span
    class="nowrap">`\[...\]`</span> (for display math) and wrapped in
    <span class="nowrap">`<span>`</span> tags with class <span
    class="nowrap">`math`</span>. Then the MathJax JavaScript will
    render it. The *URL* should point to the <span
    class="nowrap">`MathJax.js`</span> load script. If a *URL* is not
    provided, a link to the Cloudflare CDN will be inserted.

<span id="option--mathml" class="option-anchor"><span class="nowrap">`--mathml`{.option-def}</span></span>

:   Convert TeX math to [MathML](http://www.w3.org/Math/) (in <span
    class="nowrap">`epub3`</span>, <span
    class="nowrap">`docbook4`</span>, <span
    class="nowrap">`docbook5`</span>, <span
    class="nowrap">`jats`</span>, <span class="nowrap">`html4`</span>
    and <span class="nowrap">`html5`</span>). This is the default in
    <span class="nowrap">`odt`</span> output. Note that currently only
    Firefox and Safari (and select e-book readers) natively
    support MathML.

<span id="option--webtex" class="option-anchor"><span class="nowrap">`--webtex`{.option-def}</span>\[<span class="nowrap">`=`</span>*URL*\]</span>

:   Convert TeX formulas to <span class="nowrap">`<img>`</span> tags
    that link to an external script that converts formulas to images.
    The formula will be URL-encoded and concatenated with the
    URL provided. For SVG images you can for example use [<span
    class="nowrap">`--webtex https://latex.codecogs.com/svg.latex?`</span>](#option--webtex){.option}.
    If no URL is specified, the CodeCogs URL generating PNGs will be
    used (<span
    class="nowrap">`https://latex.codecogs.com/png.latex?`</span>).
    Note: the [<span
    class="nowrap">`--webtex`</span>](#option--webtex){.option} option
    will affect Markdown output as well as HTML, which is useful if
    you’re targeting a version of Markdown without native math support.

<span id="option--katex" class="option-anchor"><span class="nowrap">`--katex`{.option-def}</span>\[<span class="nowrap">`=`</span>*URL*\]</span>

:   Use [KaTeX](https://github.com/Khan/KaTeX) to display embedded TeX
    math in HTML output. The *URL* is the base URL for the
    KaTeX library. That directory should contain a <span
    class="nowrap">`katex.min.js`</span> and a <span
    class="nowrap">`katex.min.css`</span> file. If a *URL* is not
    provided, a link to the KaTeX CDN will be inserted.

<span id="option--gladtex" class="option-anchor"><span class="nowrap">`--gladtex`{.option-def}</span></span>

:   Enclose TeX math in <span class="nowrap">`<eq>`</span> tags in
    HTML output. The resulting HTML can then be processed by
    [GladTeX](http://humenda.github.io/GladTeX/) to produce images of
    the typeset formulas and an HTML file with links to these images.
    So, the procedure is:

        pandoc -s --gladtex input.md -o myfile.htex
        gladtex -d myfile-images myfile.htex
        # produces myfile.html and images in myfile-images

Options for wrapper scripts {#options-for-wrapper-scripts .options}
---------------------------

<span id="option--dump-args" class="option-anchor"><span class="nowrap">`--dump-args`{.option-def}</span></span>

:   Print information about command-line arguments to *stdout*,
    then exit. This option is intended primarily for use in
    wrapper scripts. The first line of output contains the name of the
    output file specified with the [<span
    class="nowrap">`-o`</span>](#option--output){.option} option, or
    <span class="nowrap">`-`</span> (for *stdout*) if no output file
    was specified. The remaining lines contain the command-line
    arguments, one per line, in the order they appear. These do not
    include regular pandoc options and their arguments, but do include
    any options appearing after a <span class="nowrap">`--`</span>
    separator at the end of the line.

<span id="option--ignore-args" class="option-anchor"><span class="nowrap">`--ignore-args`{.option-def}</span></span>

:   Ignore command-line arguments (for use in wrapper scripts). Regular
    pandoc options are not ignored. Thus, for example,

        pandoc --ignore-args -o foo.html -s foo.txt -- -e latin1

    is equivalent to

        pandoc -o foo.html -s

Templates
=========

When the [<span
class="nowrap">`-s/--standalone`</span>](#option--standalone){.option}
option is used, pandoc uses a template to add header and footer material
that is needed for a self-standing document. To see the default template
that is used, just type

    pandoc -D *FORMAT*

where *FORMAT* is the name of the output format. A custom template can
be specified using the [<span
class="nowrap">`--template`</span>](#option--template){.option} option.
You can also override the system default templates for a given output
format *FORMAT* by putting a file <span
class="nowrap">`templates/default.*FORMAT*`</span> in the user data
directory (see [<span
class="nowrap">`--data-dir`</span>](#option--data-dir){.option}, above).
*Exceptions:*

-   For <span class="nowrap">`odt`</span> output, customize the <span
    class="nowrap">`default.opendocument`</span> template.
-   For <span class="nowrap">`pdf`</span> output, customize the <span
    class="nowrap">`default.latex`</span> template (or the <span
    class="nowrap">`default.context`</span> template, if you use [<span
    class="nowrap">`-t context`</span>](#option--to){.option}, or the
    <span class="nowrap">`default.ms`</span> template, if you use [<span
    class="nowrap">`-t ms`</span>](#option--to){.option}, or the <span
    class="nowrap">`default.html`</span> template, if you use [<span
    class="nowrap">`-t html`</span>](#option--to){.option}).
-   <span class="nowrap">`docx`</span> and <span
    class="nowrap">`pptx`</span> have no template (however, you can use
    [<span
    class="nowrap">`--reference-doc`</span>](#option--reference-doc){.option}
    to customize the output).

Templates contain *variables*, which allow for the inclusion of
arbitrary information at any point in the file. They may be set at the
command line using the [<span
class="nowrap">`-V/--variable`</span>](#option--variable){.option}
option. If a variable is not set, pandoc will look for the key in the
document’s metadata – which can be set using either [YAML metadata
blocks](#extension-yaml_metadata_block) or with the [<span
class="nowrap">`-M/--metadata`</span>](#option--metadata){.option}
option.

Metadata variables
------------------

<span class="nowrap">`title`</span>, <span class="nowrap">`author`</span>, <span class="nowrap">`date`</span>

:   allow identification of basic aspects of the document. Included in
    PDF metadata through LaTeX and ConTeXt. These can be set through a
    [pandoc title block](#extension-pandoc_title_block), which allows
    for multiple authors, or through a YAML metadata block:

        ---
        author:
        - Aristotle
        - Peter Abelard
        ...

    Note that if you just want to set PDF or HTML metadata, without
    including a title block in the document itself, you can set the
    <span class="nowrap">`title-meta`</span>, <span
    class="nowrap">`author-meta`</span>, and <span
    class="nowrap">`date-meta`</span> variables. (By default these are
    set automatically, based on <span class="nowrap">`title`</span>,
    <span class="nowrap">`author`</span>, and <span
    class="nowrap">`date`</span>.)

<span class="nowrap">`subtitle`</span>
:   document subtitle, included in HTML, EPUB, LaTeX, ConTeXt, and docx
    documents

<span class="nowrap">`abstract`</span>
:   document summary, included in LaTeX, ConTeXt, AsciiDoc, and docx
    documents

<span class="nowrap">`keywords`</span>
:   list of keywords to be included in HTML, PDF, ODT, pptx, docx and
    AsciiDoc metadata; repeat as for <span
    class="nowrap">`author`</span>, above

<span class="nowrap">`subject`</span>
:   document subject, included in ODT, PDF, docx and pptx metadata

<span class="nowrap">`description`</span>
:   document description, included in ODT, docx and pptx metadata. Some
    applications show this as <span
    class="nowrap">`Comments`</span> metadata.

<span class="nowrap">`category`</span>
:   document category, included in docx and pptx metadata

Additionally, any root-level string metadata, not included in ODT, docx
or pptx metadata is added as a *custom property*. The following YAML
metadata block for instance:

    ---
    title:  'This is the title'
    subtitle: "This is the subtitle"
    author:
    - Author One
    - Author Two
    description: |
        This is a long
        description.

        It consists of two paragraphs
    ...

will include <span class="nowrap">`title`</span>, <span
class="nowrap">`author`</span> and <span
class="nowrap">`description`</span> as standard document properties and
<span class="nowrap">`subtitle`</span> as a custom property when
converting to docx, ODT or pptx.

Language variables
------------------

<span class="nowrap">`lang`</span>

:   identifies the main language of the document using IETF language
    tags (following the [BCP 47](https://tools.ietf.org/html/bcp47)
    standard), such as <span class="nowrap">`en`</span> or <span
    class="nowrap">`en-GB`</span>. The [Language subtag
    lookup](https://r12a.github.io/app-subtags/) tool can look up or
    verify these tags. This affects most formats, and controls
    hyphenation in PDF output when using LaTeX (through [<span
    class="nowrap">`babel`</span>](https://ctan.org/pkg/babel) and
    [<span
    class="nowrap">`polyglossia`</span>](https://ctan.org/pkg/polyglossia))
    or ConTeXt.

    Use native pandoc [Divs and Spans](#divs-and-spans) with the <span
    class="nowrap">`lang`</span> attribute to switch the language:

        ---
        lang: en-GB
        ...

        Text in the main document language (British English).

        ::: {lang=fr-CA}
        > Cette citation est écrite en français canadien.
        :::

        More text in English. ['Zitat auf Deutsch.']{lang=de}

<span class="nowrap">`dir`</span>

:   the base script direction, either <span
    class="nowrap">`rtl`</span> (right-to-left) or <span
    class="nowrap">`ltr`</span> (left-to-right).

    For bidirectional documents, native pandoc <span
    class="nowrap">`span`</span>s and <span class="nowrap">`div`</span>s
    with the <span class="nowrap">`dir`</span> attribute (value <span
    class="nowrap">`rtl`</span> or <span class="nowrap">`ltr`</span>)
    can be used to override the base direction in some output formats.
    This may not always be necessary if the final renderer (e.g. the
    browser, when generating HTML) supports the [Unicode Bidirectional
    Algorithm](http://www.w3.org/International/articles/inline-bidi-markup/uba-basics).

    When using LaTeX for bidirectional documents, only the <span
    class="nowrap">`xelatex`</span> engine is fully supported (use
    [<span
    class="nowrap">`--pdf-engine=xelatex`</span>](#option--pdf-engine){.option}).

Variables for HTML slides
-------------------------

These affect HTML output when [producing slide shows with
pandoc](#producing-slide-shows-with-pandoc). All [reveal.js
configuration
options](https://github.com/hakimel/reveal.js#configuration) are
available as variables.

<span class="nowrap">`revealjs-url`</span>
:   base URL for reveal.js documents (defaults to <span
    class="nowrap">`reveal.js`</span>)

<span class="nowrap">`s5-url`</span>
:   base URL for S5 documents (defaults to <span
    class="nowrap">`s5/default`</span>)

<span class="nowrap">`slidy-url`</span>
:   base URL for Slidy documents (defaults to <span
    class="nowrap">`https://www.w3.org/Talks/Tools/Slidy2`</span>)

<span class="nowrap">`slideous-url`</span>
:   base URL for Slideous documents (defaults to <span
    class="nowrap">`slideous`</span>)

Variables for Beamer slides
---------------------------

These variables change the appearance of PDF slides using [<span
class="nowrap">`beamer`</span>](https://ctan.org/pkg/beamer).

<span class="nowrap">`aspectratio`</span>
:   slide aspect ratio (<span class="nowrap">`43`</span> for 4:3
    \[default\], <span class="nowrap">`169`</span> for 16:9, <span
    class="nowrap">`1610`</span> for 16:10, <span
    class="nowrap">`149`</span> for 14:9, <span
    class="nowrap">`141`</span> for 1.41:1, <span
    class="nowrap">`54`</span> for 5:4, <span class="nowrap">`32`</span>
    for 3:2)

<span class="nowrap">`beamerarticle`</span>
:   produce an article from Beamer slides

<span class="nowrap">`beameroption`</span>
:   add extra beamer option with <span
    class="nowrap">`\setbeameroption{}`</span>

<span class="nowrap">`institute`</span>
:   author affiliations: can be a list when there are multiple authors

<span class="nowrap">`logo`</span>
:   logo image for slides

<span class="nowrap">`navigation`</span>
:   controls navigation symbols (default is <span
    class="nowrap">`empty`</span> for no navigation symbols; other valid
    values are <span class="nowrap">`frame`</span>, <span
    class="nowrap">`vertical`</span>, and <span
    class="nowrap">`horizontal`</span>)

<span class="nowrap">`section-titles`</span>
:   enables “title pages” for new sections (default is true)

<span class="nowrap">`theme`</span>, <span class="nowrap">`colortheme`</span>, <span class="nowrap">`fonttheme`</span>, <span class="nowrap">`innertheme`</span>, <span class="nowrap">`outertheme`</span>
:   beamer themes:

<span class="nowrap">`themeoptions`</span>
:   options for LaTeX beamer themes (a list).

<span class="nowrap">`titlegraphic`</span>
:   image for title slide

Variables for LaTeX
-------------------

Pandoc uses these variables when [creating a PDF](#creating-a-pdf) with
a LaTeX engine.

### Layout

<span class="nowrap">`block-headings`</span>

:   make <span class="nowrap">`\paragraph`</span> and <span
    class="nowrap">`\subparagraph`</span> (fourth- and fifth-level
    headings, or fifth- and sixth-level with book classes) free-standing
    rather than run-in; requires further formatting to distinguish from
    <span class="nowrap">`\subsubsection`</span> (third- or
    fourth-level headings). Instead of using this option,
    [KOMA-Script](https://ctan.org/pkg/koma-script) can adjust headings
    more extensively:

        ---
        documentclass: scrartcl
        header-includes: |
          \RedeclareSectionCommand[
            beforeskip=-10pt plus -2pt minus -1pt,
            afterskip=1sp plus -1sp minus 1sp,
            font=\normalfont\itshape]{paragraph}
          \RedeclareSectionCommand[
            beforeskip=-10pt plus -2pt minus -1pt,
            afterskip=1sp plus -1sp minus 1sp,
            font=\normalfont\scshape,
            indent=0pt]{subparagraph}
        ...

<span class="nowrap">`classoption`</span>

:   option for document class, e.g. <span
    class="nowrap">`oneside`</span>; repeat for multiple options:

        ---
        classoption:
        - twocolumn
        - landscape
        ...

<span class="nowrap">`documentclass`</span>
:   document class: usually one of the standard classes, [<span
    class="nowrap">`article`</span>](https://ctan.org/pkg/article),
    [<span class="nowrap">`book`</span>](https://ctan.org/pkg/book), and
    [<span class="nowrap">`report`</span>](https://ctan.org/pkg/report);
    the [KOMA-Script](https://ctan.org/pkg/koma-script) equivalents,
    <span class="nowrap">`scrartcl`</span>, <span
    class="nowrap">`scrbook`</span>, and <span
    class="nowrap">`scrreprt`</span>, which default to smaller margins;
    or [<span
    class="nowrap">`memoir`</span>](https://ctan.org/pkg/memoir)

<span class="nowrap">`geometry`</span>

:   option for [<span
    class="nowrap">`geometry`</span>](https://ctan.org/pkg/geometry)
    package, e.g. <span class="nowrap">`margin=1in`</span>; repeat for
    multiple options:

        ---
        geometry:
        - top=30mm
        - left=20mm
        - heightrounded
        ...

<span class="nowrap">`indent`</span>
:   uses document class settings for indentation (the default LaTeX
    template otherwise removes indentation and adds space
    between paragraphs)

<span class="nowrap">`linestretch`</span>
:   adjusts line spacing using the [<span
    class="nowrap">`setspace`</span>](https://ctan.org/pkg/setspace)
    package, e.g. <span class="nowrap">`1.25`</span>, <span
    class="nowrap">`1.5`</span>

<span class="nowrap">`margin-left`</span>, <span class="nowrap">`margin-right`</span>, <span class="nowrap">`margin-top`</span>, <span class="nowrap">`margin-bottom`</span>
:   sets margins if <span class="nowrap">`geometry`</span> is not used
    (otherwise <span class="nowrap">`geometry`</span> overrides these)

<span class="nowrap">`pagestyle`</span>
:   control <span class="nowrap">`\pagestyle{}`</span>: the default
    article class supports <span class="nowrap">`plain`</span>
    (default), <span class="nowrap">`empty`</span> (no running heads or
    page numbers), and <span class="nowrap">`headings`</span> (section
    titles in running heads)

<span class="nowrap">`papersize`</span>
:   paper size, e.g. <span class="nowrap">`letter`</span>, <span
    class="nowrap">`a4`</span>

<span class="nowrap">`secnumdepth`</span>
:   numbering depth for sections (with [<span
    class="nowrap">`--number-sections`</span>](#option--number-sections){.option}
    option or <span class="nowrap">`numbersections`</span> variable)

### Fonts

<span class="nowrap">`fontenc`</span>
:   allows font encoding to be specified through <span
    class="nowrap">`fontenc`</span> package (with <span
    class="nowrap">`pdflatex`</span>); default is <span
    class="nowrap">`T1`</span> (see [LaTeX font encodings
    guide](https://ctan.org/pkg/encguide))

<span class="nowrap">`fontfamily`</span>
:   font package for use with <span class="nowrap">`pdflatex`</span>:
    [TeX Live](http://www.tug.org/texlive/) includes many options,
    documented in the [LaTeX Font
    Catalogue](http://www.tug.dk/FontCatalogue/). The default is [Latin
    Modern](https://ctan.org/pkg/lm).

<span class="nowrap">`fontfamilyoptions`</span>

:   options for package used as <span
    class="nowrap">`fontfamily`</span>; repeat for multiple options. For
    example, to use the Libertine font with proportional
    lowercase (old-style) figures through the [<span
    class="nowrap">`libertinus`</span>](https://ctan.org/pkg/libertinus)
    package:

        ---
        fontfamily: libertinus
        fontfamilyoptions:
        - osf
        - p
        ...

<span class="nowrap">`fontsize`</span>
:   font size for body text. The standard classes allow 10pt, 11pt,
    and 12pt. To use another size, set <span
    class="nowrap">`documentclass`</span> to one of the
    [KOMA-Script](https://ctan.org/pkg/koma-script) classes, such as
    <span class="nowrap">`scrartcl`</span> or <span
    class="nowrap">`scrbook`</span>.

<span class="nowrap">`mainfont`</span>, <span class="nowrap">`sansfont`</span>, <span class="nowrap">`monofont`</span>, <span class="nowrap">`mathfont`</span>, <span class="nowrap">`CJKmainfont`</span>
:   font families for use with <span class="nowrap">`xelatex`</span> or
    <span class="nowrap">`lualatex`</span>: take the name of any system
    font, using the [<span
    class="nowrap">`fontspec`</span>](https://ctan.org/pkg/fontspec) package.
    <span class="nowrap">`CJKmainfont`</span> uses the [<span
    class="nowrap">`xecjk`</span>](https://ctan.org/pkg/xecjk) package.

<span class="nowrap">`mainfontoptions`</span>, <span class="nowrap">`sansfontoptions`</span>, <span class="nowrap">`monofontoptions`</span>, <span class="nowrap">`mathfontoptions`</span>, <span class="nowrap">`CJKoptions`</span>

:   options to use with <span class="nowrap">`mainfont`</span>, <span
    class="nowrap">`sansfont`</span>, <span
    class="nowrap">`monofont`</span>, <span
    class="nowrap">`mathfont`</span>, <span
    class="nowrap">`CJKmainfont`</span> in <span
    class="nowrap">`xelatex`</span> and <span
    class="nowrap">`lualatex`</span>. Allow for any choices available
    through [<span
    class="nowrap">`fontspec`</span>](https://ctan.org/pkg/fontspec);
    repeat for multiple options. For example, to use the [TeX
    Gyre](http://www.gust.org.pl/projects/e-foundry/tex-gyre) version of
    Palatino with lowercase figures:

        ---
        mainfont: TeX Gyre Pagella
        mainfontoptions:
        - Numbers=Lowercase
        - Numbers=Proportional
        ...

<span class="nowrap">`microtypeoptions`</span>
:   options to pass to the microtype package

### Links

<span class="nowrap">`colorlinks`</span>
:   add color to link text; automatically enabled if any of <span
    class="nowrap">`linkcolor`</span>, <span
    class="nowrap">`filecolor`</span>, <span
    class="nowrap">`citecolor`</span>, <span
    class="nowrap">`urlcolor`</span>, or <span
    class="nowrap">`toccolor`</span> are set

<span class="nowrap">`linkcolor`</span>, <span class="nowrap">`filecolor`</span>, <span class="nowrap">`citecolor`</span>, <span class="nowrap">`urlcolor`</span>, <span class="nowrap">`toccolor`</span>
:   color for internal links, external links, citation links, linked
    URLs, and links in table of contents, respectively: uses options
    allowed by [<span
    class="nowrap">`xcolor`</span>](https://ctan.org/pkg/xcolor),
    including the <span class="nowrap">`dvipsnames`</span>, <span
    class="nowrap">`svgnames`</span>, and <span
    class="nowrap">`x11names`</span> lists

<span class="nowrap">`links-as-notes`</span>
:   causes links to be printed as footnotes

### Front matter

<span class="nowrap">`lof`</span>, <span class="nowrap">`lot`</span>
:   include list of figures, list of tables

<span class="nowrap">`thanks`</span>
:   contents of acknowledgments footnote after document title

<span class="nowrap">`toc`</span>
:   include table of contents (can also be set using [<span
    class="nowrap">`--toc/--table-of-contents`</span>](#option--toc){.option})

<span class="nowrap">`toc-depth`</span>
:   level of section to include in table of contents

### BibLaTeX Bibliographies

These variables function when using BibLaTeX for [citation
rendering](#citation-rendering).

<span class="nowrap">`biblatexoptions`</span>
:   list of options for biblatex

<span class="nowrap">`biblio-style`</span>
:   bibliography style, when used with [<span
    class="nowrap">`--natbib`</span>](#option--natbib){.option} and
    [<span
    class="nowrap">`--biblatex`</span>](#option--biblatex){.option}.

<span class="nowrap">`biblio-title`</span>
:   bibliography title, when used with [<span
    class="nowrap">`--natbib`</span>](#option--natbib){.option} and
    [<span
    class="nowrap">`--biblatex`</span>](#option--biblatex){.option}.

<span class="nowrap">`bibliography`</span>
:   bibliography to use for resolving references

<span class="nowrap">`natbiboptions`</span>
:   list of options for natbib

Variables for ConTeXt
---------------------

Pandoc uses these variables when [creating a PDF](#creating-a-pdf) with
ConTeXt.

<span class="nowrap">`fontsize`</span>
:   font size for body text (e.g. <span class="nowrap">`10pt`</span>,
    <span class="nowrap">`12pt`</span>)

<span class="nowrap">`headertext`</span>, <span class="nowrap">`footertext`</span>
:   text to be placed in running header or footer (see [ConTeXt Headers
    and Footers](https://wiki.contextgarden.net/Headers_and_Footers));
    repeat up to four times for different placement

<span class="nowrap">`indenting`</span>
:   controls indentation of paragraphs, e.g. <span
    class="nowrap">`yes,small,next`</span> (see [ConTeXt
    Indentation](https://wiki.contextgarden.net/Indentation)); repeat
    for multiple options

<span class="nowrap">`interlinespace`</span>
:   adjusts line spacing, e.g. <span class="nowrap">`4ex`</span> (using
    [<span
    class="nowrap">`setupinterlinespace`</span>](https://wiki.contextgarden.net/Command/setupinterlinespace));
    repeat for multiple options

<span class="nowrap">`layout`</span>
:   options for page margins and text arrangement (see [ConTeXt
    Layout](https://wiki.contextgarden.net/Layout)); repeat for multiple
    options

<span class="nowrap">`linkcolor`</span>, <span class="nowrap">`contrastcolor`</span>
:   color for links outside and inside a page, e.g. <span
    class="nowrap">`red`</span>, <span class="nowrap">`blue`</span> (see
    [ConTeXt Color](https://wiki.contextgarden.net/Color))

<span class="nowrap">`linkstyle`</span>
:   typeface style for links, e.g. <span class="nowrap">`normal`</span>,
    <span class="nowrap">`bold`</span>, <span
    class="nowrap">`slanted`</span>, <span
    class="nowrap">`boldslanted`</span>, <span
    class="nowrap">`type`</span>, <span class="nowrap">`cap`</span>,
    <span class="nowrap">`small`</span>

<span class="nowrap">`lof`</span>, <span class="nowrap">`lot`</span>
:   include list of figures, list of tables

<span class="nowrap">`mainfont`</span>, <span class="nowrap">`sansfont`</span>, <span class="nowrap">`monofont`</span>, <span class="nowrap">`mathfont`</span>
:   font families: take the name of any system font (see [ConTeXt Font
    Switching](https://wiki.contextgarden.net/Font_Switching))

<span class="nowrap">`margin-left`</span>, <span class="nowrap">`margin-right`</span>, <span class="nowrap">`margin-top`</span>, <span class="nowrap">`margin-bottom`</span>
:   sets margins, if <span class="nowrap">`layout`</span> is not used
    (otherwise <span class="nowrap">`layout`</span> overrides these)

<span class="nowrap">`pagenumbering`</span>
:   page number style and location (using [<span
    class="nowrap">`setuppagenumbering`</span>](https://wiki.contextgarden.net/Command/setuppagenumbering));
    repeat for multiple options

<span class="nowrap">`papersize`</span>
:   paper size, e.g. <span class="nowrap">`letter`</span>, <span
    class="nowrap">`A4`</span>, <span class="nowrap">`landscape`</span>
    (see [ConTeXt Paper
    Setup](https://wiki.contextgarden.net/PaperSetup)); repeat for
    multiple options

<span class="nowrap">`pdfa`</span>
:   adds to the preamble the setup necessary to generate PDF/A-1b:2005.
    To successfully generate PDF/A the required ICC color profiles have
    to be available and the content and all included files (such
    as images) have to be standard conforming. The ICC profiles can be
    obtained from [ConTeXt ICC
    Profiles](https://wiki.contextgarden.net/PDFX#ICC_profiles). See
    also [ConTeXt PDFA](https://wiki.contextgarden.net/PDF/A) for
    more details.

<span class="nowrap">`toc`</span>
:   include table of contents (can also be set using [<span
    class="nowrap">`--toc/--table-of-contents`</span>](#option--toc){.option})

<span class="nowrap">`whitespace`</span>
:   spacing between paragraphs, e.g. <span class="nowrap">`none`</span>,
    <span class="nowrap">`small`</span> (using [<span
    class="nowrap">`setupwhitespace`</span>](https://wiki.contextgarden.net/Command/setupwhitespace))

Variables for <span class="nowrap">`wkhtmltopdf`</span>
-------------------------------------------------------

Pandoc uses these variables when [creating a PDF](#creating-a-pdf) with
[<span class="nowrap">`wkhtmltopdf`</span>](https://wkhtmltopdf.org).
The [<span class="nowrap">`--css`</span>](#option--css){.option} option
also affects the output.

<span class="nowrap">`footer-html`</span>, <span class="nowrap">`header-html`</span>
:   add information to the header and footer

<span class="nowrap">`margin-left`</span>, <span class="nowrap">`margin-right`</span>, <span class="nowrap">`margin-top`</span>, <span class="nowrap">`margin-bottom`</span>
:   set the page margins

<span class="nowrap">`papersize`</span>
:   sets the PDF paper size

Variables for man pages
-----------------------

<span class="nowrap">`adjusting`</span>
:   adjusts text to left (<span class="nowrap">`l`</span>), right (<span
    class="nowrap">`r`</span>), center (<span
    class="nowrap">`c`</span>), or both (<span
    class="nowrap">`b`</span>) margins

<span class="nowrap">`footer`</span>
:   footer in man pages

<span class="nowrap">`header`</span>
:   header in man pages

<span class="nowrap">`hyphenate`</span>
:   if <span class="nowrap">`true`</span> (the default), hyphenation
    will be used

<span class="nowrap">`section`</span>
:   section number in man pages

Variables for ms
----------------

<span class="nowrap">`fontfamily`</span>
:   font family (e.g. <span class="nowrap">`T`</span> or <span
    class="nowrap">`P`</span>)

<span class="nowrap">`indent`</span>
:   paragraph indent (e.g. <span class="nowrap">`2m`</span>)

<span class="nowrap">`lineheight`</span>
:   line height (e.g. <span class="nowrap">`12p`</span>)

<span class="nowrap">`pointsize`</span>
:   point size (e.g. <span class="nowrap">`10p`</span>)

Structural variables
--------------------

Pandoc sets these variables automatically in response to
[options](#options) or document contents; users can also modify them.
These vary depending on the output format, and include the following:

<span class="nowrap">`body`</span>
:   body of document

<span class="nowrap">`date-meta`</span>
:   the <span class="nowrap">`date`</span> variable converted to ISO
    8601 YYYY-MM-DD, included in all HTML based formats (dzslides, epub,
    html, html4, html5, revealjs, s5, slideous, slidy). The recognized
    formats for <span class="nowrap">`date`</span> are: <span
    class="nowrap">`mm/dd/yyyy`</span>, <span
    class="nowrap">`mm/dd/yy`</span>, <span
    class="nowrap">`yyyy-mm-dd`</span> (ISO 8601), <span
    class="nowrap">`dd MM yyyy`</span> (e.g. either <span
    class="nowrap">`02 Apr 2018`</span> or <span
    class="nowrap">`02 April 2018`</span>), <span
    class="nowrap">`MM dd, yyyy`</span> (e.g. <span
    class="nowrap">`Apr. 02, 2018`</span> or <span
    class="nowrap">`April 02, 2018),`</span>yyyy\[mm\[dd\]\]\]<span
    class="nowrap">`(e.g.`</span>20180402, <span
    class="nowrap">`201804`</span> or <span
    class="nowrap">`2018`</span>).

<span class="nowrap">`header-includes`</span>
:   contents specified by [<span
    class="nowrap">`-H/--include-in-header`</span>](#option--include-in-header){.option}
    (may have multiple values)

<span class="nowrap">`include-before`</span>
:   contents specified by [<span
    class="nowrap">`-B/--include-before-body`</span>](#option--include-before-body){.option}
    (may have multiple values)

<span class="nowrap">`include-after`</span>
:   contents specified by [<span
    class="nowrap">`-A/--include-after-body`</span>](#option--include-after-body){.option}
    (may have multiple values)

<span class="nowrap">`meta-json`</span>
:   JSON representation of all of the document’s metadata. Field values
    are transformed to the selected output format.

<span class="nowrap">`numbersections`</span>
:   non-null value if [<span
    class="nowrap">`-N/--number-sections`</span>](#option--number-sections){.option}
    was specified

<span class="nowrap">`sourcefile`</span>, <span class="nowrap">`outputfile`</span>

:   source and destination filenames, as given on the command line.
    <span class="nowrap">`sourcefile`</span> can also be a list if input
    comes from multiple files, or empty if input is from stdin. You can
    use the following snippet in your template to distinguish them:

        $if(sourcefile)$
        $for(sourcefile)$
        $sourcefile$
        $endfor$
        $else$
        (stdin)
        $endif$

    Similarly, <span class="nowrap">`outputfile`</span> can be <span
    class="nowrap">`-`</span> if output goes to the terminal.

    If you need absolute paths, use e.g. <span
    class="nowrap">`$curdir$/$sourcefile$`</span>.

<span class="nowrap">`curdir`</span>
:   working directory from which pandoc is run.

<span class="nowrap">`toc`</span>
:   non-null value if [<span
    class="nowrap">`--toc/--table-of-contents`</span>](#option--toc){.option}
    was specified

<span class="nowrap">`toc-title`</span>
:   title of table of contents (works only with EPUB, opendocument, odt,
    docx, pptx, beamer, LaTeX)

Using variables in templates
----------------------------

Variable names are sequences of alphanumerics, <span
class="nowrap">`-`</span>, and <span class="nowrap">`_`</span>, starting
with a letter. A variable name surrounded by <span
class="nowrap">`$`</span> signs will be replaced by its value. For
example, the string <span class="nowrap">`$title$`</span> in

    <title>$title$</title>

will be replaced by the document title.

To write a literal <span class="nowrap">`$`</span> in a template, use
<span class="nowrap">`$$`</span>.

Templates may contain conditionals. The syntax is as follows:

    $if(variable)$
    X
    $else$
    Y
    $endif$

This will include <span class="nowrap">`X`</span> in the template if
<span class="nowrap">`variable`</span> has a truthy value; otherwise it
will include <span class="nowrap">`Y`</span>. Here a truthy value is any
of the following:

-   a string that is not entirely white space,
-   a non-empty array where the first value is truthy,
-   any number (including zero),
-   any object,
-   the boolean <span class="nowrap">`true`</span> (to specify the
    boolean <span class="nowrap">`true`</span> value using YAML metadata
    or the [<span
    class="nowrap">`--metadata`</span>](#option--metadata){.option}
    flag, use <span class="nowrap">`true`</span>, <span
    class="nowrap">`True`</span>, or <span class="nowrap">`TRUE`</span>;
    with the [<span
    class="nowrap">`--variable`</span>](#option--variable){.option}
    flag, simply omit a value for the variable, e.g. [<span
    class="nowrap">`--variable draft`</span>](#option--variable){.option}).

<span class="nowrap">`X`</span> and <span class="nowrap">`Y`</span> are
placeholders for any valid template text, and may include interpolated
variables or other conditionals. The <span
class="nowrap">`$else$`</span> section may be omitted.

When variables can have multiple values (for example, <span
class="nowrap">`author`</span> in a multi-author document), you can use
the <span class="nowrap">`$for$`</span> keyword:

    $for(author)$
    <meta name="author" content="$author$" />
    $endfor$

You can optionally specify a separator to be used between consecutive
items:

    $for(author)$$author$$sep$, $endfor$

Note that the separator needs to be specified immediately before the
<span class="nowrap">`$endfor`</span> keyword.

A dot can be used to select a field of a variable that takes an object
as its value. So, for example:

    $author.name$ ($author.affiliation$)

The value of a variable will be indented to the same level as the
variable.

If you use custom templates, you may need to revise them as pandoc
changes. We recommend tracking the changes in the default templates, and
modifying your custom templates accordingly. An easy way to do this is
to fork the [pandoc-templates](https://github.com/jgm/pandoc-templates)
repository and merge in changes after each pandoc release.

Templates may contain comments: anything on a line after <span
class="nowrap">`$--`</span> will be treated as a comment and ignored.

Extensions
==========

The behavior of some of the readers and writers can be adjusted by
enabling or disabling various extensions.

An extension can be enabled by adding <span
class="nowrap">`+EXTENSION`</span> to the format name and disabled by
adding <span class="nowrap">`-EXTENSION`</span>. For example, [<span
class="nowrap">`--from markdown_strict+footnotes`</span>](#option--from){.option}
is strict Markdown with footnotes enabled, while [<span
class="nowrap">`--from markdown-footnotes-pipe_tables`</span>](#option--from){.option}
is pandoc’s Markdown without footnotes or pipe tables.

The markdown reader and writer make by far the most use of extensions.
Extensions only used by them are therefore covered in the section
[Pandoc’s Markdown](#pandocs-markdown) below (See [Markdown
variants](#markdown-variants) for <span
class="nowrap">`commonmark`</span> and <span
class="nowrap">`gfm`</span>.) In the following, extensions that also
work for other formats are covered.

Note that markdown extensions added to the <span
class="nowrap">`ipynb`</span> format affect Markdown cells in Jupyter
notebooks (as do command-line options like [<span
class="nowrap">`--atx-headers`</span>](#option--atx-headers){.option}).

Typography
----------

#### Extension: <span class="nowrap">`smart`</span>

Interpret straight quotes as curly quotes, <span
class="nowrap">`---`</span> as em-dashes, <span
class="nowrap">`--`</span> as en-dashes, and <span
class="nowrap">`...`</span> as ellipses. Nonbreaking spaces are inserted
after certain abbreviations, such as “Mr.”

This extension can be enabled/disabled for the following formats:

input formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`commonmark`</span>, <span
    class="nowrap">`latex`</span>, <span
    class="nowrap">`mediawiki`</span>, <span
    class="nowrap">`org`</span>, <span class="nowrap">`rst`</span>,
    <span class="nowrap">`twiki`</span>

output formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`latex`</span>, <span
    class="nowrap">`context`</span>, <span class="nowrap">`rst`</span>

enabled by default in
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`latex`</span>, <span class="nowrap">`context`</span>
    (both input and output)

Note: If you are *writing* Markdown, then the <span
class="nowrap">`smart`</span> extension has the reverse effect: what
would have been curly quotes comes out straight.

In LaTeX, <span class="nowrap">`smart`</span> means to use the standard
TeX ligatures for quotation marks (<span
class="nowrap">``` `` ```</span> and <span class="nowrap">`''`</span>
for double quotes, <span class="nowrap">`` ` ``</span> and <span
class="nowrap">`'`</span> for single quotes) and dashes (<span
class="nowrap">`--`</span> for en-dash and <span
class="nowrap">`---`</span> for em-dash). If <span
class="nowrap">`smart`</span> is disabled, then in reading LaTeX pandoc
will parse these characters literally. In writing LaTeX, enabling <span
class="nowrap">`smart`</span> tells pandoc to use the ligatures when
possible; if <span class="nowrap">`smart`</span> is disabled pandoc will
use unicode quotation mark and dash characters.

Headings and sections
---------------------

#### Extension: <span class="nowrap">`auto_identifiers`</span>

A heading without an explicitly specified identifier will be
automatically assigned a unique identifier based on the heading text.

This extension can be enabled/disabled for the following formats:

input formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`latex`</span>, <span class="nowrap">`rst`</span>,
    <span class="nowrap">`mediawiki`</span>, <span
    class="nowrap">`textile`</span>

output formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`muse`</span>

enabled by default in
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`muse`</span>

The default algorithm used to derive the identifier from the heading
text is:

-   Remove all formatting, links, etc.
-   Remove all footnotes.
-   Remove all non-alphanumeric characters, except underscores, hyphens,
    and periods.
-   Replace all spaces and newlines with hyphens.
-   Convert all alphabetic characters to lowercase.
-   Remove everything up to the first letter (identifiers may not begin
    with a number or punctuation mark).
-   If nothing is left after this, use the identifier <span
    class="nowrap">`section`</span>.

Thus, for example,

  Heading                                                     Identifier
  ----------------------------------------------------------- -----------------------------------------------------------
  <span class="nowrap">`Heading identifiers in HTML`</span>   <span class="nowrap">`heading-identifiers-in-html`</span>
  <span class="nowrap">`Maître d'hôtel`</span>                <span class="nowrap">`maître-dhôtel`</span>
  <span class="nowrap">`*Dogs*?--in *my* house?`</span>       <span class="nowrap">`dogs--in-my-house`</span>
  <span class="nowrap">`[HTML], [S5], or [RTF]?`</span>       <span class="nowrap">`html-s5-or-rtf`</span>
  <span class="nowrap">`3. Applications`</span>               <span class="nowrap">`applications`</span>
  <span class="nowrap">`33`</span>                            <span class="nowrap">`section`</span>

These rules should, in most cases, allow one to determine the identifier
from the heading text. The exception is when several headings have the
same text; in this case, the first will get an identifier as described
above; the second will get the same identifier with <span
class="nowrap">`-1`</span> appended; the third with <span
class="nowrap">`-2`</span>; and so on.

(However, a different algorithm is used if <span
class="nowrap">`gfm_auto_identifiers`</span> is enabled; see below.)

These identifiers are used to provide link targets in the table of
contents generated by the [<span
class="nowrap">`--toc|--table-of-contents`</span>](#option--toc){.option}
option. They also make it easy to provide links from one section of a
document to another. A link to this section, for example, might look
like this:

    See the section on
    [heading identifiers](#heading-identifiers-in-html-latex-and-context).

Note, however, that this method of providing links to sections works
only in HTML, LaTeX, and ConTeXt formats.

If the [<span
class="nowrap">`--section-divs`</span>](#option--section-divs){.option}
option is specified, then each section will be wrapped in a <span
class="nowrap">`section`</span> (or a <span class="nowrap">`div`</span>,
if <span class="nowrap">`html4`</span> was specified), and the
identifier will be attached to the enclosing <span
class="nowrap">`<section>`</span> (or <span
class="nowrap">`<div>`</span>) tag rather than the heading itself. This
allows entire sections to be manipulated using JavaScript or treated
differently in CSS.

#### Extension: <span class="nowrap">`ascii_identifiers`</span>

Causes the identifiers produced by <span
class="nowrap">`auto_identifiers`</span> to be pure ASCII. Accents are
stripped off of accented Latin letters, and non-Latin letters are
omitted.

#### Extension: <span class="nowrap">`gfm_auto_identifiers`</span>

Changes the algorithm used by <span
class="nowrap">`auto_identifiers`</span> to conform to GitHub’s method.
Spaces are converted to dashes (<span class="nowrap">`-`</span>),
uppercase characters to lowercase characters, and punctuation characters
other than <span class="nowrap">`-`</span> and <span
class="nowrap">`_`</span> are removed.

Math Input
----------

The extensions [<span
class="nowrap">`tex_math_dollars`</span>](#extension-tex_math_dollars),
[<span
class="nowrap">`tex_math_single_backslash`</span>](#extension-tex_math_single_backslash),
and [<span
class="nowrap">`tex_math_double_backslash`</span>](#extension-tex_math_double_backslash)
are described in the section about Pandoc’s Markdown.

However, they can also be used with HTML input. This is handy for
reading web pages formatted using MathJax, for example.

Raw HTML/TeX
------------

The following extensions (especially how they affect Markdown
input/output) are also described in more detail in their respective
sections of [Pandoc’s Markdown](#pandocs-markdown).

#### Extension: <span class="nowrap">`raw_html`</span> {#raw_html}

When converting from HTML, parse elements to raw HTML which are not
representable in pandoc’s AST. By default, this is disabled for HTML
input.

#### Extension: <span class="nowrap">`raw_tex`</span> {#raw_tex}

Allows raw LaTeX, TeX, and ConTeXt to be included in a document.

This extension can be enabled/disabled for the following formats (in
addition to <span class="nowrap">`markdown`</span>):

input formats
:   <span class="nowrap">`latex`</span>, <span
    class="nowrap">`org`</span>, <span class="nowrap">`textile`</span>,
    <span class="nowrap">`html`</span> (environments, <span
    class="nowrap">`\ref`</span>, and <span
    class="nowrap">`\eqref`</span> only), <span
    class="nowrap">`ipynb`</span>

output formats
:   <span class="nowrap">`textile`</span>, <span
    class="nowrap">`commonmark`</span>

Note: as applied to <span class="nowrap">`ipynb`</span>, <span
class="nowrap">`raw_html`</span> and <span
class="nowrap">`raw_tex`</span> affect not only raw TeX in markdown
cells, but data with mime type <span class="nowrap">`text/html`</span>
in output cells. Since the <span class="nowrap">`ipynb`</span> reader
attempts to preserve the richest possible outputs when several options
are given, you will get best results if you disable <span
class="nowrap">`raw_html`</span> and <span
class="nowrap">`raw_tex`</span> when converting to formats like <span
class="nowrap">`docx`</span> which don’t allow raw <span
class="nowrap">`html`</span> or <span class="nowrap">`tex`</span>.

#### Extension: <span class="nowrap">`native_divs`</span> {#native_divs}

This extension is enabled by default for HTML input. This means that
<span class="nowrap">`div`</span>s are parsed to pandoc native elements.
(Alternatively, you can parse them to raw HTML using [<span
class="nowrap">`-f html-native_divs+raw_html`</span>](#option--from){.option}.)

When converting HTML to Markdown, for example, you may want to drop all
<span class="nowrap">`div`</span>s and <span
class="nowrap">`span`</span>s:

    pandoc -f html-native_divs-native_spans -t markdown

#### Extension: <span class="nowrap">`native_spans`</span> {#native_spans}

Analogous to <span class="nowrap">`native_divs`</span> above.

Literate Haskell support
------------------------

#### Extension: <span class="nowrap">`literate_haskell`</span>

Treat the document as literate Haskell source.

This extension can be enabled/disabled for the following formats:

input formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`rst`</span>, <span class="nowrap">`latex`</span>

output formats
:   <span class="nowrap">`markdown`</span>, <span
    class="nowrap">`rst`</span>, <span class="nowrap">`latex`</span>,
    <span class="nowrap">`html`</span>

If you append <span class="nowrap">`+lhs`</span> (or <span
class="nowrap">`+literate_haskell`</span>) to one of the formats above,
pandoc will treat the document as literate Haskell source. This means
that

-   In Markdown input, “bird track” sections will be parsed as Haskell
    code rather than block quotations. Text between <span
    class="nowrap">`\begin{code}`</span> and <span
    class="nowrap">`\end{code}`</span> will also be treated as
    Haskell code. For ATX-style headings the character ‘=’ will be used
    instead of ‘\#’.

-   In Markdown output, code blocks with classes <span
    class="nowrap">`haskell`</span> and <span
    class="nowrap">`literate`</span> will be rendered using bird tracks,
    and block quotations will be indented one space, so they will not be
    treated as Haskell code. In addition, headings will be rendered
    setext-style (with underlines) rather than ATX-style (with
    ‘\#’ characters). (This is because ghc treats ‘\#’ characters in
    column 1 as introducing line numbers.)

-   In restructured text input, “bird track” sections will be parsed as
    Haskell code.

-   In restructured text output, code blocks with class <span
    class="nowrap">`haskell`</span> will be rendered using bird tracks.

-   In LaTeX input, text in <span class="nowrap">`code`</span>
    environments will be parsed as Haskell code.

-   In LaTeX output, code blocks with class <span
    class="nowrap">`haskell`</span> will be rendered inside <span
    class="nowrap">`code`</span> environments.

-   In HTML output, code blocks with class <span
    class="nowrap">`haskell`</span> will be rendered with class <span
    class="nowrap">`literatehaskell`</span> and bird tracks.

Examples:

    pandoc -f markdown+lhs -t html

reads literate Haskell source formatted with Markdown conventions and
writes ordinary HTML (without bird tracks).

    pandoc -f markdown+lhs -t html+lhs

writes HTML with the Haskell code in bird tracks, so it can be copied
and pasted as literate Haskell source.

Note that GHC expects the bird tracks in the first column, so indented
literate code blocks (e.g. inside an itemized environment) will not be
picked up by the Haskell compiler.

Other extensions
----------------

#### Extension: <span class="nowrap">`empty_paragraphs`</span>

Allows empty paragraphs. By default empty paragraphs are omitted.

This extension can be enabled/disabled for the following formats:

input formats
:   <span class="nowrap">`docx`</span>, <span
    class="nowrap">`html`</span>

output formats
:   <span class="nowrap">`docx`</span>, <span
    class="nowrap">`odt`</span>, <span
    class="nowrap">`opendocument`</span>, <span
    class="nowrap">`html`</span>

#### Extension: <span class="nowrap">`styles`</span> {#ext-styles}

When converting from docx, read all docx styles as divs (for paragraph
styles) and spans (for character styles) regardless of whether pandoc
understands the meaning of these styles. This can be used with [docx
custom styles](#custom-styles). Disabled by default.

input formats
:   <span class="nowrap">`docx`</span>

#### Extension: <span class="nowrap">`amuse`</span>

In the <span class="nowrap">`muse`</span> input format, this enables
Text::Amuse extensions to Emacs Muse markup.

#### Extension: <span class="nowrap">`citations`</span> {#org-citations}

Some aspects of [Pandoc’s Markdown citation syntax](#citations) are also
accepted in <span class="nowrap">`org`</span> input.

#### Extension: <span class="nowrap">`ntb`</span>

In the <span class="nowrap">`context`</span> output format this enables
the use of [Natural Tables (TABLE)](http://wiki.contextgarden.net/TABLE)
instead of the default [Extreme Tables
(xtables)](http://wiki.contextgarden.net/xtables). Natural tables allow
more fine-grained global customization but come at a performance penalty
compared to extreme tables.

Pandoc’s Markdown
=================

Pandoc understands an extended and slightly revised version of John
Gruber’s [Markdown](http://daringfireball.net/projects/markdown/)
syntax. This document explains the syntax, noting differences from
standard Markdown. Except where noted, these differences can be
suppressed by using the <span class="nowrap">`markdown_strict`</span>
format instead of <span class="nowrap">`markdown`</span>. Extensions can
be enabled or disabled to specify the behavior more granularly. They are
described in the following. See also [Extensions](#extensions) above,
for extensions that work also on other formats.

Philosophy
----------

Markdown is designed to be easy to write, and, even more importantly,
easy to read:

> A Markdown-formatted document should be publishable as-is, as plain
> text, without looking like it’s been marked up with tags or formatting
> instructions. – [John
> Gruber](http://daringfireball.net/projects/markdown/syntax#philosophy)

This principle has guided pandoc’s decisions in finding syntax for
tables, footnotes, and other extensions.

There is, however, one respect in which pandoc’s aims are different from
the original aims of Markdown. Whereas Markdown was originally designed
with HTML generation in mind, pandoc is designed for multiple output
formats. Thus, while pandoc allows the embedding of raw HTML, it
discourages it, and provides other, non-HTMLish ways of representing
important document elements like definition lists, tables, mathematics,
and footnotes.

Paragraphs
----------

A paragraph is one or more lines of text followed by one or more blank
lines. Newlines are treated as spaces, so you can reflow your paragraphs
as you like. If you need a hard line break, put two or more spaces at
the end of a line.

#### Extension: <span class="nowrap">`escaped_line_breaks`</span>

A backslash followed by a newline is also a hard line break. Note: in
multiline and grid table cells, this is the only way to create a hard
line break, since trailing spaces in the cells are ignored.

Headings
--------

There are two kinds of headings: Setext and ATX.

### Setext-style headings

A setext-style heading is a line of text “underlined” with a row of
<span class="nowrap">`=`</span> signs (for a level-one heading) or <span
class="nowrap">`-`</span> signs (for a level-two heading):

    A level-one heading
    ===================

    A level-two heading
    -------------------

The heading text can contain inline formatting, such as emphasis (see
[Inline formatting](#inline-formatting), below).

### ATX-style headings

An ATX-style heading consists of one to six <span
class="nowrap">`#`</span> signs and a line of text, optionally followed
by any number of <span class="nowrap">`#`</span> signs. The number of
<span class="nowrap">`#`</span> signs at the beginning of the line is
the heading level:

    ## A level-two heading

    ### A level-three heading ###

As with setext-style headings, the heading text can contain formatting:

    # A level-one heading with a [link](/url) and *emphasis*

#### Extension: <span class="nowrap">`blank_before_header`</span>

Standard Markdown syntax does not require a blank line before a heading.
Pandoc does require this (except, of course, at the beginning of the
document). The reason for the requirement is that it is all too easy for
a <span class="nowrap">`#`</span> to end up at the beginning of a line
by accident (perhaps through line wrapping). Consider, for example:

    I like several of their flavors of ice cream:
    #22, for example, and #5.

#### Extension: <span class="nowrap">`space_in_atx_header`</span>

Many Markdown implementations do not require a space between the opening
<span class="nowrap">`#`</span>s of an ATX heading and the heading text,
so that <span class="nowrap">`#5 bolt`</span> and <span
class="nowrap">`#hashtag`</span> count as headings. With this extension,
pandoc does require the space.

### Heading identifiers

See also the [<span class="nowrap">`auto_identifiers`</span>
extension](#extension-auto_identifiers) above.

#### Extension: <span class="nowrap">`header_attributes`</span>

Headings can be assigned attributes using this syntax at the end of the
line containing the heading text:

    {#identifier .class .class key=value key=value}

Thus, for example, the following headings will all be assigned the
identifier <span class="nowrap">`foo`</span>:

    # My heading {#foo}

    ## My heading ##    {#foo}

    My other heading   {#foo}
    ---------------

(This syntax is compatible with [PHP Markdown
Extra](https://michelf.ca/projects/php-markdown/extra/).)

Note that although this syntax allows assignment of classes and
key/value attributes, writers generally don’t use all of this
information. Identifiers, classes, and key/value attributes are used in
HTML and HTML-based formats such as EPUB and slidy. Identifiers are used
for labels and link anchors in the LaTeX, ConTeXt, Textile, Jira markup,
and AsciiDoc writers.

Headings with the class <span class="nowrap">`unnumbered`</span> will
not be numbered, even if [<span
class="nowrap">`--number-sections`</span>](#option--number-sections){.option}
is specified. A single hyphen (<span class="nowrap">`-`</span>) in an
attribute context is equivalent to <span
class="nowrap">`.unnumbered`</span>, and preferable in non-English
documents. So,

    # My heading {-}

is just the same as

    # My heading {.unnumbered}

#### Extension: <span class="nowrap">`implicit_header_references`</span>

Pandoc behaves as if reference links have been defined for each heading.
So, to link to a heading

    # Heading identifiers in HTML

you can simply write

    [Heading identifiers in HTML]

or

    [Heading identifiers in HTML][]

or

    [the section on heading identifiers][heading identifiers in
    HTML]

instead of giving the identifier explicitly:

    [Heading identifiers in HTML](#heading-identifiers-in-html)

If there are multiple headings with identical text, the corresponding
reference will link to the first one only, and you will need to use
explicit links to link to the others, as described above.

Like regular reference links, these references are case-insensitive.

Explicit link reference definitions always take priority over implicit
heading references. So, in the following example, the link will point to
<span class="nowrap">`bar`</span>, not to <span
class="nowrap">`#foo`</span>:

    # Foo

    [foo]: bar

    See [foo]

Block quotations
----------------

Markdown uses email conventions for quoting blocks of text. A block
quotation is one or more paragraphs or other block elements (such as
lists or headings), with each line preceded by a <span
class="nowrap">`>`</span> character and an optional space. (The <span
class="nowrap">`>`</span> need not start at the left margin, but it
should not be indented more than three spaces.)

    > This is a block quote. This
    > paragraph has two lines.
    >
    > 1. This is a list inside a block quote.
    > 2. Second item.

A “lazy” form, which requires the <span class="nowrap">`>`</span>
character only on the first line of each block, is also allowed:

    > This is a block quote. This
    paragraph has two lines.

    > 1. This is a list inside a block quote.
    2. Second item.

Among the block elements that can be contained in a block quote are
other block quotes. That is, block quotes can be nested:

    > This is a block quote.
    >
    > > A block quote within a block quote.

If the <span class="nowrap">`>`</span> character is followed by an
optional space, that space will be considered part of the block quote
marker and not part of the indentation of the contents. Thus, to put an
indented code block in a block quote, you need five spaces after the
<span class="nowrap">`>`</span>:

    >     code

#### Extension: <span class="nowrap">`blank_before_blockquote`</span>

Standard Markdown syntax does not require a blank line before a block
quote. Pandoc does require this (except, of course, at the beginning of
the document). The reason for the requirement is that it is all too easy
for a <span class="nowrap">`>`</span> to end up at the beginning of a
line by accident (perhaps through line wrapping). So, unless the <span
class="nowrap">`markdown_strict`</span> format is used, the following
does not produce a nested block quote in pandoc:

    > This is a block quote.
    >> Nested.

Verbatim (code) blocks
----------------------

### Indented code blocks

A block of text indented four spaces (or one tab) is treated as verbatim
text: that is, special characters do not trigger special formatting, and
all spaces and line breaks are preserved. For example,

        if (a > 3) {
          moveShip(5 * gravity, DOWN);
        }

The initial (four space or one tab) indentation is not considered part
of the verbatim text, and is removed in the output.

Note: blank lines in the verbatim text need not begin with four spaces.

### Fenced code blocks

#### Extension: <span class="nowrap">`fenced_code_blocks`</span>

In addition to standard indented code blocks, pandoc supports *fenced*
code blocks. These begin with a row of three or more tildes (<span
class="nowrap">`~`</span>) and end with a row of tildes that must be at
least as long as the starting row. Everything between these lines is
treated as code. No indentation is necessary:

    ~~~~~~~
    if (a > 3) {
      moveShip(5 * gravity, DOWN);
    }
    ~~~~~~~

Like regular code blocks, fenced code blocks must be separated from
surrounding text by blank lines.

If the code itself contains a row of tildes or backticks, just use a
longer row of tildes or backticks at the start and end:

    ~~~~~~~~~~~~~~~~
    ~~~~~~~~~~
    code including tildes
    ~~~~~~~~~~
    ~~~~~~~~~~~~~~~~

#### Extension: <span class="nowrap">`backtick_code_blocks`</span>

Same as <span class="nowrap">`fenced_code_blocks`</span>, but uses
backticks (<span class="nowrap">`` ` ``</span>) instead of tildes (<span
class="nowrap">`~`</span>).

#### Extension: <span class="nowrap">`fenced_code_attributes`</span>

Optionally, you may attach attributes to fenced or backtick code block
using this syntax:

    ~~~~ {#mycode .haskell .numberLines startFrom="100"}
    qsort []     = []
    qsort (x:xs) = qsort (filter (< x) xs) ++ [x] ++
                   qsort (filter (>= x) xs)
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Here <span class="nowrap">`mycode`</span> is an identifier, <span
class="nowrap">`haskell`</span> and <span
class="nowrap">`numberLines`</span> are classes, and <span
class="nowrap">`startFrom`</span> is an attribute with value <span
class="nowrap">`100`</span>. Some output formats can use this
information to do syntax highlighting. Currently, the only output
formats that uses this information are HTML, LaTeX, Docx, Ms, and
PowerPoint. If highlighting is supported for your output format and
language, then the code block above will appear highlighted, with
numbered lines. (To see which languages are supported, type <span
class="nowrap">`pandoc --list-highlight-languages`</span>.) Otherwise,
the code block above will appear as follows:

    <pre id="mycode" class="haskell numberLines" startFrom="100">
      <code>
      ...
      </code>
    </pre>

The <span class="nowrap">`numberLines`</span> (or <span
class="nowrap">`number-lines`</span>) class will cause the lines of the
code block to be numbered, starting with <span class="nowrap">`1`</span>
or the value of the <span class="nowrap">`startFrom`</span> attribute.
The <span class="nowrap">`lineAnchors`</span> (or <span
class="nowrap">`line-anchors`</span>) class will cause the lines to be
clickable anchors in HTML output.

A shortcut form can also be used for specifying the language of the code
block:

    ```haskell
    qsort [] = []
    ```

This is equivalent to:

    ``` {.haskell}
    qsort [] = []
    ```

If the <span class="nowrap">`fenced_code_attributes`</span> extension is
disabled, but input contains class attribute(s) for the code block, the
first class attribute will be printed after the opening fence as a bare
word.

To prevent all highlighting, use the [<span
class="nowrap">`--no-highlight`</span>](#option--no-highlight){.option}
flag. To set the highlighting style, use [<span
class="nowrap">`--highlight-style`</span>](#option--highlight-style){.option}.
For more information on highlighting, see [Syntax
highlighting](#syntax-highlighting), below.

Line blocks
-----------

#### Extension: <span class="nowrap">`line_blocks`</span>

A line block is a sequence of lines beginning with a vertical bar (<span
class="nowrap">`|`</span>) followed by a space. The division into lines
will be preserved in the output, as will any leading spaces; otherwise,
the lines will be formatted as Markdown. This is useful for verse and
addresses:

    | The limerick packs laughs anatomical
    | In space that is quite economical.
    |    But the good ones I've seen
    |    So seldom are clean
    | And the clean ones so seldom are comical

    | 200 Main St.
    | Berkeley, CA 94718

The lines can be hard-wrapped if needed, but the continuation line must
begin with a space.

    | The Right Honorable Most Venerable and Righteous Samuel L.
      Constable, Jr.
    | 200 Main St.
    | Berkeley, CA 94718

This syntax is borrowed from
[reStructuredText](http://docutils.sourceforge.net/docs/ref/rst/introduction.html).

Lists
-----

### Bullet lists

A bullet list is a list of bulleted list items. A bulleted list item
begins with a bullet (<span class="nowrap">`*`</span>, <span
class="nowrap">`+`</span>, or <span class="nowrap">`-`</span>). Here is
a simple example:

    * one
    * two
    * three

This will produce a “compact” list. If you want a “loose” list, in which
each item is formatted as a paragraph, put spaces between the items:

    * one

    * two

    * three

The bullets need not be flush with the left margin; they may be indented
one, two, or three spaces. The bullet must be followed by whitespace.

List items look best if subsequent lines are flush with the first line
(after the bullet):

    * here is my first
      list item.
    * and my second.

But Markdown also allows a “lazy” format:

    * here is my first
    list item.
    * and my second.

### Block content in list items

A list item may contain multiple paragraphs and other block-level
content. However, subsequent paragraphs must be preceded by a blank line
and indented to line up with the first non-space content after the list
marker.

      * First paragraph.

        Continued.

      * Second paragraph. With a code block, which must be indented
        eight spaces:

            { code }

Exception: if the list marker is followed by an indented code block,
which must begin 5 spaces after the list marker, then subsequent
paragraphs must begin two columns after the last character of the list
marker:

    *     code

      continuation paragraph

List items may include other lists. In this case the preceding blank
line is optional. The nested list must be indented to line up with the
first non-space character after the list marker of the containing list
item.

    * fruits
      + apples
        - macintosh
        - red delicious
      + pears
      + peaches
    * vegetables
      + broccoli
      + chard

As noted above, Markdown allows you to write list items “lazily,”
instead of indenting continuation lines. However, if there are multiple
paragraphs or other blocks in a list item, the first line of each must
be indented.

    + A lazy, lazy, list
    item.

    + Another one; this looks
    bad but is legal.

        Second paragraph of second
    list item.

### Ordered lists

Ordered lists work just like bulleted lists, except that the items begin
with enumerators rather than bullets.

In standard Markdown, enumerators are decimal numbers followed by a
period and a space. The numbers themselves are ignored, so there is no
difference between this list:

    1.  one
    2.  two
    3.  three

and this one:

    5.  one
    7.  two
    1.  three

#### Extension: <span class="nowrap">`fancy_lists`</span>

Unlike standard Markdown, pandoc allows ordered list items to be marked
with uppercase and lowercase letters and roman numerals, in addition to
Arabic numerals. List markers may be enclosed in parentheses or followed
by a single right-parentheses or period. They must be separated from the
text that follows by at least one space, and, if the list marker is a
capital letter with a period, by at least two spaces.[^1^](#fn1){#fnref1
.footnote-ref}

The <span class="nowrap">`fancy_lists`</span> extension also allows
‘<span class="nowrap">`#`</span>’ to be used as an ordered list marker
in place of a numeral:

    #. one
    #. two

#### Extension: <span class="nowrap">`startnum`</span>

Pandoc also pays attention to the type of list marker used, and to the
starting number, and both of these are preserved where possible in the
output format. Thus, the following yields a list with numbers followed
by a single parenthesis, starting with 9, and a sublist with lowercase
roman numerals:

     9)  Ninth
    10)  Tenth
    11)  Eleventh
           i. subone
          ii. subtwo
         iii. subthree

Pandoc will start a new list each time a different type of list marker
is used. So, the following will create three lists:

    (2) Two
    (5) Three
    1.  Four
    *   Five

If default list markers are desired, use <span
class="nowrap">`#.`</span>:

    #.  one
    #.  two
    #.  three

#### Extension: <span class="nowrap">`task_lists`</span>

Pandoc supports task lists, using the syntax of GitHub-Flavored
Markdown.

    - [ ] an unchecked task list item
    - [x] checked item

### Definition lists

#### Extension: <span class="nowrap">`definition_lists`</span>

Pandoc supports definition lists, using the syntax of [PHP Markdown
Extra](https://michelf.ca/projects/php-markdown/extra/) with some
extensions.[^2^](#fn2){#fnref2 .footnote-ref}

    Term 1

    :   Definition 1

    Term 2 with *inline markup*

    :   Definition 2

            { some code, part of Definition 2 }

        Third paragraph of definition 2.

Each term must fit on one line, which may optionally be followed by a
blank line, and must be followed by one or more definitions. A
definition begins with a colon or tilde, which may be indented one or
two spaces.

A term may have multiple definitions, and each definition may consist of
one or more block elements (paragraph, code block, list, etc.), each
indented four spaces or one tab stop. The body of the definition
(including the first line, aside from the colon or tilde) should be
indented four spaces. However, as with other Markdown lists, you can
“lazily” omit indentation except at the beginning of a paragraph or
other block element:

    Term 1

    :   Definition
    with lazy continuation.

        Second paragraph of the definition.

If you leave space before the definition (as in the example above), the
text of the definition will be treated as a paragraph. In some output
formats, this will mean greater spacing between term/definition pairs.
For a more compact definition list, omit the space before the
definition:

    Term 1
      ~ Definition 1

    Term 2
      ~ Definition 2a
      ~ Definition 2b

Note that space between items in a definition list is required. (A
variant that loosens this requirement, but disallows “lazy” hard
wrapping, can be activated with <span
class="nowrap">`compact_definition_lists`</span>: see [Non-pandoc
extensions](#non-pandoc-extensions), below.)

### Numbered example lists

#### Extension: <span class="nowrap">`example_lists`</span>

The special list marker <span class="nowrap">`@`</span> can be used for
sequentially numbered examples. The first list item with a <span
class="nowrap">`@`</span> marker will be numbered ‘1’, the next ‘2’, and
so on, throughout the document. The numbered examples need not occur in
a single list; each new list using <span class="nowrap">`@`</span> will
take up where the last stopped. So, for example:

    (@)  My first example will be numbered (1).
    (@)  My second example will be numbered (2).

    Explanation of examples.

    (@)  My third example will be numbered (3).

Numbered examples can be labeled and referred to elsewhere in the
document:

    (@good)  This is a good example.

    As (@good) illustrates, ...

The label can be any string of alphanumeric characters, underscores, or
hyphens.

Note: continuation paragraphs in example lists must always be indented
four spaces, regardless of the length of the list marker. That is,
example lists always behave as if the <span
class="nowrap">`four_space_rule`</span> extension is set. This is
because example labels tend to be long, and indenting content to the
first non-space character after the label would be awkward.

### Compact and loose lists

Pandoc behaves differently from <span
class="nowrap">`Markdown.pl`</span> on some “edge cases” involving
lists. Consider this source:

    +   First
    +   Second:
        -   Fee
        -   Fie
        -   Foe

    +   Third

Pandoc transforms this into a “compact list” (with no <span
class="nowrap">`<p>`</span> tags around “First”, “Second”, or “Third”),
while Markdown puts <span class="nowrap">`<p>`</span> tags around
“Second” and “Third” (but not “First”), because of the blank space
around “Third”. Pandoc follows a simple rule: if the text is followed by
a blank line, it is treated as a paragraph. Since “Second” is followed
by a list, and not a blank line, it isn’t treated as a paragraph. The
fact that the list is followed by a blank line is irrelevant. (Note:
Pandoc works this way even when the <span
class="nowrap">`markdown_strict`</span> format is specified. This
behavior is consistent with the official Markdown syntax description,
even though it is different from that of <span
class="nowrap">`Markdown.pl`</span>.)

### Ending a list

What if you want to put an indented code block after a list?

    -   item one
    -   item two

        { my code block }

Trouble! Here pandoc (like other Markdown implementations) will treat
<span class="nowrap">`{ my code block }`</span> as the second paragraph
of item two, and not as a code block.

To “cut off” the list after item two, you can insert some non-indented
content, like an HTML comment, which won’t produce visible output in any
format:

    -   item one
    -   item two

    <!-- end of list -->

        { my code block }

You can use the same trick if you want two consecutive lists instead of
one big list:

    1.  one
    2.  two
    3.  three

    <!-- -->

    1.  uno
    2.  dos
    3.  tres

Horizontal rules
----------------

A line containing a row of three or more <span
class="nowrap">`*`</span>, <span class="nowrap">`-`</span>, or <span
class="nowrap">`_`</span> characters (optionally separated by spaces)
produces a horizontal rule:

    *  *  *  *

    ---------------

Tables
------

Four kinds of tables may be used. The first three kinds presuppose the
use of a fixed-width font, such as Courier. The fourth kind can be used
with proportionally spaced fonts, as it does not require lining up
columns.

#### Extension: <span class="nowrap">`table_captions`</span>

A caption may optionally be provided with all 4 kinds of tables (as
illustrated in the examples below). A caption is a paragraph beginning
with the string <span class="nowrap">`Table:`</span> (or just <span
class="nowrap">`:`</span>), which will be stripped off. It may appear
either before or after the table.

#### Extension: <span class="nowrap">`simple_tables`</span>

Simple tables look like this:

      Right     Left     Center     Default
    -------     ------ ----------   -------
         12     12        12            12
        123     123       123          123
          1     1          1             1

    Table:  Demonstration of simple table syntax.

The header and table rows must each fit on one line. Column alignments
are determined by the position of the header text relative to the dashed
line below it:[^3^](#fn3){#fnref3 .footnote-ref}

-   If the dashed line is flush with the header text on the right side
    but extends beyond it on the left, the column is right-aligned.
-   If the dashed line is flush with the header text on the left side
    but extends beyond it on the right, the column is left-aligned.
-   If the dashed line extends beyond the header text on both sides, the
    column is centered.
-   If the dashed line is flush with the header text on both sides, the
    default alignment is used (in most cases, this will be left).

The table must end with a blank line, or a line of dashes followed by a
blank line.

The column header row may be omitted, provided a dashed line is used to
end the table. For example:

    -------     ------ ----------   -------
         12     12        12             12
        123     123       123           123
          1     1          1              1
    -------     ------ ----------   -------

When the header row is omitted, column alignments are determined on the
basis of the first line of the table body. So, in the tables above, the
columns would be right, left, center, and right aligned, respectively.

#### Extension: <span class="nowrap">`multiline_tables`</span>

Multiline tables allow header and table rows to span multiple lines of
text (but cells that span multiple columns or rows of the table are not
supported). Here is an example:

    -------------------------------------------------------------
     Centered   Default           Right Left
      Header    Aligned         Aligned Aligned
    ----------- ------- --------------- -------------------------
       First    row                12.0 Example of a row that
                                        spans multiple lines.

      Second    row                 5.0 Here's another one. Note
                                        the blank line between
                                        rows.
    -------------------------------------------------------------

    Table: Here's the caption. It, too, may span
    multiple lines.

These work like simple tables, but with the following differences:

-   They must begin with a row of dashes, before the header text (unless
    the header row is omitted).
-   They must end with a row of dashes, then a blank line.
-   The rows must be separated by blank lines.

In multiline tables, the table parser pays attention to the widths of
the columns, and the writers try to reproduce these relative widths in
the output. So, if you find that one of the columns is too narrow in the
output, try widening it in the Markdown source.

The header may be omitted in multiline tables as well as simple tables:

    ----------- ------- --------------- -------------------------
       First    row                12.0 Example of a row that
                                        spans multiple lines.

      Second    row                 5.0 Here's another one. Note
                                        the blank line between
                                        rows.
    ----------- ------- --------------- -------------------------

    : Here's a multiline table without a header.

It is possible for a multiline table to have just one row, but the row
should be followed by a blank line (and then the row of dashes that ends
the table), or the table may be interpreted as a simple table.

#### Extension: <span class="nowrap">`grid_tables`</span>

Grid tables look like this:

    : Sample grid table.

    +---------------+---------------+--------------------+
    | Fruit         | Price         | Advantages         |
    +===============+===============+====================+
    | Bananas       | $1.34         | - built-in wrapper |
    |               |               | - bright color     |
    +---------------+---------------+--------------------+
    | Oranges       | $2.10         | - cures scurvy     |
    |               |               | - tasty            |
    +---------------+---------------+--------------------+

The row of <span class="nowrap">`=`</span>s separates the header from
the table body, and can be omitted for a headerless table. The cells of
grid tables may contain arbitrary block elements (multiple paragraphs,
code blocks, lists, etc.). Cells that span multiple columns or rows are
not supported. Grid tables can be created easily using [Emacs table
mode](http://table.sourceforge.net/).

Alignments can be specified as with pipe tables, by putting colons at
the boundaries of the separator line after the header:

    +---------------+---------------+--------------------+
    | Right         | Left          | Centered           |
    +==============:+:==============+:==================:+
    | Bananas       | $1.34         | built-in wrapper   |
    +---------------+---------------+--------------------+

For headerless tables, the colons go on the top line instead:

    +--------------:+:--------------+:------------------:+
    | Right         | Left          | Centered           |
    +---------------+---------------+--------------------+

##### Grid Table Limitations

Pandoc does not support grid tables with row spans or column spans. This
means that neither variable numbers of columns across rows nor variable
numbers of rows across columns are supported by Pandoc. All grid tables
must have the same number of columns in each row, and the same number of
rows in each column. For example, the Docutils [sample grid
tables](http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#grid-tables)
will not render as expected with Pandoc.

#### Extension: <span class="nowrap">`pipe_tables`</span>

Pipe tables look like this:

    | Right | Left | Default | Center |
    |------:|:-----|---------|:------:|
    |   12  |  12  |    12   |    12  |
    |  123  |  123 |   123   |   123  |
    |    1  |    1 |     1   |     1  |

      : Demonstration of pipe table syntax.

The syntax is identical to [PHP Markdown Extra
tables](https://michelf.ca/projects/php-markdown/extra/#table). The
beginning and ending pipe characters are optional, but pipes are
required between all columns. The colons indicate column alignment as
shown. The header cannot be omitted. To simulate a headerless table,
include a header with blank cells.

Since the pipes indicate column boundaries, columns need not be
vertically aligned, as they are in the above example. So, this is a
perfectly legal (though ugly) pipe table:

    fruit| price
    -----|-----:
    apple|2.05
    pear|1.37
    orange|3.09

The cells of pipe tables cannot contain block elements like paragraphs
and lists, and cannot span multiple lines. If a pipe table contains a
row whose printable content is wider than the column width (see [<span
class="nowrap">`--columns`</span>](#option--columns){.option}), then the
table will take up the full text width and the cell contents will wrap,
with the relative cell widths determined by the number of dashes in the
line separating the table header from the table body. (For example <span
class="nowrap">`---|-`</span> would make the first column 3/4 and the
second column 1/4 of the full text width.) On the other hand, if no
lines are wider than column width, then cell contents will not be
wrapped, and the cells will be sized to their contents.

Note: pandoc also recognizes pipe tables of the following form, as can
be produced by Emacs’ orgtbl-mode:

    | One | Two   |
    |-----+-------|
    | my  | table |
    | is  | nice  |

The difference is that <span class="nowrap">`+`</span> is used instead
of <span class="nowrap">`|`</span>. Other orgtbl features are not
supported. In particular, to get non-default column alignment, you’ll
need to add colons as above.

Metadata blocks
---------------

#### Extension: <span class="nowrap">`pandoc_title_block`</span>

If the file begins with a title block

    % title
    % author(s) (separated by semicolons)
    % date

it will be parsed as bibliographic information, not regular text. (It
will be used, for example, in the title of standalone LaTeX or HTML
output.) The block may contain just a title, a title and an author, or
all three elements. If you want to include an author but no title, or a
title and a date but no author, you need a blank line:

    %
    % Author

    % My title
    %
    % June 15, 2006

The title may occupy multiple lines, but continuation lines must begin
with leading space, thus:

    % My title
      on multiple lines

If a document has multiple authors, the authors may be put on separate
lines with leading space, or separated by semicolons, or both. So, all
of the following are equivalent:

    % Author One
      Author Two

    % Author One; Author Two

    % Author One;
      Author Two

The date must fit on one line.

All three metadata fields may contain standard inline formatting
(italics, links, footnotes, etc.).

Title blocks will always be parsed, but they will affect the output only
when the [<span
class="nowrap">`--standalone`</span>](#option--standalone){.option}
([<span class="nowrap">`-s`</span>](#option--standalone){.option})
option is chosen. In HTML output, titles will appear twice: once in the
document head – this is the title that will appear at the top of the
window in a browser – and once at the beginning of the document body.
The title in the document head can have an optional prefix attached
([<span
class="nowrap">`--title-prefix`</span>](#option--title-prefix){.option}
or [<span class="nowrap">`-T`</span>](#option--title-prefix){.option}
option). The title in the body appears as an H1 element with class
“title”, so it can be suppressed or reformatted with CSS. If a title
prefix is specified with [<span
class="nowrap">`-T`</span>](#option--title-prefix){.option} and no title
block appears in the document, the title prefix will be used by itself
as the HTML title.

The man page writer extracts a title, man page section number, and other
header and footer information from the title line. The title is assumed
to be the first word on the title line, which may optionally end with a
(single-digit) section number in parentheses. (There should be no space
between the title and the parentheses.) Anything after this is assumed
to be additional footer and header text. A single pipe character (<span
class="nowrap">`|`</span>) should be used to separate the footer text
from the header text. Thus,

    % PANDOC(1)

will yield a man page with the title <span
class="nowrap">`PANDOC`</span> and section 1.

    % PANDOC(1) Pandoc User Manuals

will also have “Pandoc User Manuals” in the footer.

    % PANDOC(1) Pandoc User Manuals | Version 4.0

will also have “Version 4.0” in the header.

#### Extension: <span class="nowrap">`yaml_metadata_block`</span>

A YAML metadata block is a valid YAML object, delimited by a line of
three hyphens (<span class="nowrap">`---`</span>) at the top and a line
of three hyphens (<span class="nowrap">`---`</span>) or three dots
(<span class="nowrap">`...`</span>) at the bottom. A YAML metadata block
may occur anywhere in the document, but if it is not at the beginning,
it must be preceded by a blank line. (Note that, because of the way
pandoc concatenates input files when several are provided, you may also
keep the metadata in a separate YAML file and pass it to pandoc as an
argument, along with your Markdown files:

    pandoc chap1.md chap2.md chap3.md metadata.yaml -s -o book.html

Just be sure that the YAML file begins with <span
class="nowrap">`---`</span> and ends with <span
class="nowrap">`---`</span> or <span class="nowrap">`...`</span>.)
Alternatively, you can use the [<span
class="nowrap">`--metadata-file`</span>](#option--metadata-file){.option}
option. Using that approach however, you cannot reference content (like
footnotes) from the main markdown input document.

Metadata will be taken from the fields of the YAML object and added to
any existing document metadata. Metadata can contain lists and objects
(nested arbitrarily), but all string scalars will be interpreted as
Markdown. Fields with names ending in an underscore will be ignored by
pandoc. (They may be given a role by external processors.) Field names
must not be interpretable as YAML numbers or boolean values (so, for
example, <span class="nowrap">`yes`</span>, <span
class="nowrap">`True`</span>, and <span class="nowrap">`15`</span>
cannot be used as field names).

A document may contain multiple metadata blocks. The metadata fields
will be combined through a *left-biased union*: if two metadata blocks
attempt to set the same field, the value from the first block will be
taken.

When pandoc is used with [<span
class="nowrap">`-t markdown`</span>](#option--to){.option} to create a
Markdown document, a YAML metadata block will be produced only if the
[<span
class="nowrap">`-s/--standalone`</span>](#option--standalone){.option}
option is used. All of the metadata will appear in a single block at the
beginning of the document.

Note that YAML escaping rules must be followed. Thus, for example, if a
title contains a colon, it must be quoted. The pipe character (<span
class="nowrap">`|`</span>) can be used to begin an indented block that
will be interpreted literally, without need for escaping. This form is
necessary when the field contains blank lines or block-level formatting:

    ---
    title:  'This is the title: it contains a colon'
    author:
    - Author One
    - Author Two
    keywords: [nothing, nothingness]
    abstract: |
      This is the abstract.

      It consists of two paragraphs.
    ...

Template variables will be set automatically from the metadata. Thus,
for example, in writing HTML, the variable <span
class="nowrap">`abstract`</span> will be set to the HTML equivalent of
the Markdown in the <span class="nowrap">`abstract`</span> field:

    <p>This is the abstract.</p>
    <p>It consists of two paragraphs.</p>

Variables can contain arbitrary YAML structures, but the template must
match this structure. The <span class="nowrap">`author`</span> variable
in the default templates expects a simple list or string, but can be
changed to support more complicated structures. The following
combination, for example, would add an affiliation to the author if one
is given:

    ---
    title: The document title
    author:
    - name: Author One
      affiliation: University of Somewhere
    - name: Author Two
      affiliation: University of Nowhere
    ...

To use the structured authors in the example above, you would need a
custom template:

    $for(author)$
    $if(author.name)$
    $author.name$$if(author.affiliation)$ ($author.affiliation$)$endif$
    $else$
    $author$
    $endif$
    $endfor$

Raw content to include in the document’s header may be specified using
<span class="nowrap">`header-includes`</span>; however, it is important
to mark up this content as raw code for a particular output format,
using the [<span class="nowrap">`raw_attribute`</span>
extension](#extension-raw_attribute)), or it will be interpreted as
markdown. For example:

    header-includes:
    - |
      ```{=latex}
      \let\oldsection\section
      \renewcommand{\section}[1]{\clearpage\oldsection{#1}}
      ```

Backslash escapes
-----------------

#### Extension: <span class="nowrap">`all_symbols_escapable`</span>

Except inside a code block or inline code, any punctuation or space
character preceded by a backslash will be treated literally, even if it
would normally indicate formatting. Thus, for example, if one writes

    *\*hello\**

one will get

    <em>*hello*</em>

instead of

    <strong>hello</strong>

This rule is easier to remember than standard Markdown’s rule, which
allows only the following characters to be backslash-escaped:

    \`*_{}[]()>#+-.!

(However, if the <span class="nowrap">`markdown_strict`</span> format is
used, the standard Markdown rule will be used.)

A backslash-escaped space is parsed as a nonbreaking space. It will
appear in TeX output as <span class="nowrap">`~`</span> and in HTML and
XML as <span class="nowrap">`\&#160;`</span> or <span
class="nowrap">`\&nbsp;`</span>.

A backslash-escaped newline (i.e. a backslash occurring at the end of a
line) is parsed as a hard line break. It will appear in TeX output as
<span class="nowrap">`\\`</span> and in HTML as <span
class="nowrap">`<br />`</span>. This is a nice alternative to Markdown’s
“invisible” way of indicating hard line breaks using two trailing spaces
on a line.

Backslash escapes do not work in verbatim contexts.

Inline formatting
-----------------

### Emphasis

To *emphasize* some text, surround it with <span
class="nowrap">`*`</span>s or <span class="nowrap">`_`</span>, like
this:

    This text is _emphasized with underscores_, and this
    is *emphasized with asterisks*.

Double <span class="nowrap">`*`</span> or <span
class="nowrap">`_`</span> produces **strong emphasis**:

    This is **strong emphasis** and __with underscores__.

A <span class="nowrap">`*`</span> or <span class="nowrap">`_`</span>
character surrounded by spaces, or backslash-escaped, will not trigger
emphasis:

    This is * not emphasized *, and \*neither is this\*.

#### Extension: <span class="nowrap">`intraword_underscores`</span>

Because <span class="nowrap">`_`</span> is sometimes used inside words
and identifiers, pandoc does not interpret a <span
class="nowrap">`_`</span> surrounded by alphanumeric characters as an
emphasis marker. If you want to emphasize just part of a word, use <span
class="nowrap">`*`</span>:

    feas*ible*, not feas*able*.

### Strikeout

#### Extension: <span class="nowrap">`strikeout`</span>

To strikeout a section of text with a horizontal line, begin and end it
with <span class="nowrap">`~~`</span>. Thus, for example,

    This ~~is deleted text.~~

### Superscripts and subscripts

#### Extension: <span class="nowrap">`superscript`</span>, <span class="nowrap">`subscript`</span>

Superscripts may be written by surrounding the superscripted text by
<span class="nowrap">`^`</span> characters; subscripts may be written by
surrounding the subscripted text by <span class="nowrap">`~`</span>
characters. Thus, for example,

    H~2~O is a liquid.  2^10^ is 1024.

If the superscripted or subscripted text contains spaces, these spaces
must be escaped with backslashes. (This is to prevent accidental
superscripting and subscripting through the ordinary use of <span
class="nowrap">`~`</span> and <span class="nowrap">`^`</span>.) Thus, if
you want the letter P with ‘a cat’ in subscripts, use <span
class="nowrap">`P~a\ cat~`</span>, not <span
class="nowrap">`P~a cat~`</span>.

### Verbatim

To make a short span of text verbatim, put it inside backticks:

    What is the difference between `>>=` and `>>`?

If the verbatim text includes a backtick, use double backticks:

    Here is a literal backtick `` ` ``.

(The spaces after the opening backticks and before the closing backticks
will be ignored.)

The general rule is that a verbatim span starts with a string of
consecutive backticks (optionally followed by a space) and ends with a
string of the same number of backticks (optionally preceded by a space).

Note that backslash-escapes (and other Markdown constructs) do not work
in verbatim contexts:

    This is a backslash followed by an asterisk: `\*`.

#### Extension: <span class="nowrap">`inline_code_attributes`</span>

Attributes can be attached to verbatim text, just as with [fenced code
blocks](#fenced-code-blocks):

    `<$>`{.haskell}

### Small caps

To write small caps, use the <span class="nowrap">`smallcaps`</span>
class:

    [Small caps]{.smallcaps}

Or, without the <span class="nowrap">`bracketed_spans`</span> extension:

    <span class="smallcaps">Small caps</span>

For compatibility with other Markdown flavors, CSS is also supported:

    <span style="font-variant:small-caps;">Small caps</span>

This will work in all output formats that support small caps.

Math
----

#### Extension: <span class="nowrap">`tex_math_dollars`</span>

Anything between two <span class="nowrap">`$`</span> characters will be
treated as TeX math. The opening <span class="nowrap">`$`</span> must
have a non-space character immediately to its right, while the closing
<span class="nowrap">`$`</span> must have a non-space character
immediately to its left, and must not be followed immediately by a
digit. Thus, <span class="nowrap">`$20,000 and $30,000`</span> won’t
parse as math. If for some reason you need to enclose text in literal
<span class="nowrap">`$`</span> characters, backslash-escape them and
they won’t be treated as math delimiters.

TeX math will be printed in all output formats. How it is rendered
depends on the output format:

LaTeX
:   It will appear verbatim surrounded by <span
    class="nowrap">`\(...\)`</span> (for inline math) or <span
    class="nowrap">`\[...\]`</span> (for display math).

Markdown, Emacs Org mode, ConTeXt, ZimWiki
:   It will appear verbatim surrounded by <span
    class="nowrap">`$...$`</span> (for inline math) or <span
    class="nowrap">`$$...$$`</span> (for display math).

XWiki
:   It will appear verbatim surrounded by <span
    class="nowrap">`{{formula}}..{{/formula}}`</span>.

reStructuredText
:   It will be rendered using an [interpreted text role <span
    class="nowrap">`:math:`</span>](http://docutils.sourceforge.net/docs/ref/rst/roles.html#math).

AsciiDoc
:   For AsciiDoc output format ([<span
    class="nowrap">`-t asciidoc`</span>](#option--to){.option}) it will
    appear verbatim surrounded by <span
    class="nowrap">`latexmath:[$...$]`</span> (for inline math) or <span
    class="nowrap">`[latexmath]++++\[...\]+++`</span> (for
    display math). For AsciiDoctor output format ([<span
    class="nowrap">`-t asciidoctor`</span>](#option--to){.option}) the
    LaTex delimiters (<span class="nowrap">`$..$`</span> and <span
    class="nowrap">`\[..\]`</span>) are omitted.

Texinfo
:   It will be rendered inside a <span
    class="nowrap">`@math`</span> command.

roff man, Jira markup
:   It will be rendered verbatim without <span
    class="nowrap">`$`</span>’s.

MediaWiki, DokuWiki
:   It will be rendered inside <span
    class="nowrap">`<math>`</span> tags.

Textile
:   It will be rendered inside <span
    class="nowrap">`<span class="math">`</span> tags.

RTF, OpenDocument
:   It will be rendered, if possible, using Unicode characters, and will
    otherwise appear verbatim.

ODT
:   It will be rendered, if possible, using MathML.

DocBook
:   If the [<span
    class="nowrap">`--mathml`</span>](#option--mathml){.option} flag is
    used, it will be rendered using MathML in an <span
    class="nowrap">`inlineequation`</span> or <span
    class="nowrap">`informalequation`</span> tag. Otherwise it will be
    rendered, if possible, using Unicode characters.

Docx
:   It will be rendered using OMML math markup.

FictionBook2
:   If the [<span
    class="nowrap">`--webtex`</span>](#option--webtex){.option} option
    is used, formulas are rendered as images using CodeCogs or other
    compatible web service, downloaded and embedded in the e-book.
    Otherwise, they will appear verbatim.

HTML, Slidy, DZSlides, S5, EPUB
:   The way math is rendered in HTML will depend on the command-line
    options selected. Therefore see [Math rendering in
    HTML](#math-rendering-in-html) above.

Raw HTML
--------

#### Extension: <span class="nowrap">`raw_html`</span> {#extension-raw_html}

Markdown allows you to insert raw HTML (or DocBook) anywhere in a
document (except verbatim contexts, where <span
class="nowrap">`<`</span>, <span class="nowrap">`>`</span>, and <span
class="nowrap">`&`</span> are interpreted literally). (Technically this
is not an extension, since standard Markdown allows it, but it has been
made an extension so that it can be disabled if desired.)

The raw HTML is passed through unchanged in HTML, S5, Slidy, Slideous,
DZSlides, EPUB, Markdown, CommonMark, Emacs Org mode, and Textile
output, and suppressed in other formats.

For a more explicit way of including raw HTML in a Markdown document,
see the [<span class="nowrap">`raw_attribute`</span>
extension](#extension-raw_attribute).

In the CommonMark format, if <span class="nowrap">`raw_html`</span> is
enabled, superscripts, subscripts, strikeouts and small capitals will be
represented as HTML. Otherwise, plain-text fallbacks will be used. Note
that even if <span class="nowrap">`raw_html`</span> is disabled, tables
will be rendered with HTML syntax if they cannot use pipe syntax.

#### Extension: <span class="nowrap">`markdown_in_html_blocks`</span>

Standard Markdown allows you to include HTML “blocks”: blocks of HTML
between balanced tags that are separated from the surrounding text with
blank lines, and start and end at the left margin. Within these blocks,
everything is interpreted as HTML, not Markdown; so (for example), <span
class="nowrap">`*`</span> does not signify emphasis.

Pandoc behaves this way when the <span
class="nowrap">`markdown_strict`</span> format is used; but by default,
pandoc interprets material between HTML block tags as Markdown. Thus,
for example, pandoc will turn

    <table>
    <tr>
    <td>*one*</td>
    <td>[a link](http://google.com)</td>
    </tr>
    </table>

into

    <table>
    <tr>
    <td><em>one</em></td>
    <td><a href="http://google.com">a link</a></td>
    </tr>
    </table>

whereas <span class="nowrap">`Markdown.pl`</span> will preserve it as
is.

There is one exception to this rule: text between <span
class="nowrap">`<script>`</span> and <span
class="nowrap">`<style>`</span> tags is not interpreted as Markdown.

This departure from standard Markdown should make it easier to mix
Markdown with HTML block elements. For example, one can surround a block
of Markdown text with <span class="nowrap">`<div>`</span> tags without
preventing it from being interpreted as Markdown.

#### Extension: <span class="nowrap">`native_divs`</span> {#extension-native_divs}

Use native pandoc <span class="nowrap">`Div`</span> blocks for content
inside <span class="nowrap">`<div>`</span> tags. For the most part this
should give the same output as <span
class="nowrap">`markdown_in_html_blocks`</span>, but it makes it easier
to write pandoc filters to manipulate groups of blocks.

#### Extension: <span class="nowrap">`native_spans`</span> {#extension-native_spans}

Use native pandoc <span class="nowrap">`Span`</span> blocks for content
inside <span class="nowrap">`<span>`</span> tags. For the most part this
should give the same output as <span class="nowrap">`raw_html`</span>,
but it makes it easier to write pandoc filters to manipulate groups of
inlines.

#### Extension: <span class="nowrap">`raw_tex`</span> {#extension-raw_tex}

In addition to raw HTML, pandoc allows raw LaTeX, TeX, and ConTeXt to be
included in a document. Inline TeX commands will be preserved and passed
unchanged to the LaTeX and ConTeXt writers. Thus, for example, you can
use LaTeX to include BibTeX citations:

    This result was proved in \cite{jones.1967}.

Note that in LaTeX environments, like

    \begin{tabular}{|l|l|}\hline
    Age & Frequency \\ \hline
    18--25  & 15 \\
    26--35  & 33 \\
    36--45  & 22 \\ \hline
    \end{tabular}

the material between the begin and end tags will be interpreted as raw
LaTeX, not as Markdown.

For a more explicit and flexible way of including raw TeX in a Markdown
document, see the [<span class="nowrap">`raw_attribute`</span>
extension](#extension-raw_attribute).

Inline LaTeX is ignored in output formats other than Markdown, LaTeX,
Emacs Org mode, and ConTeXt.

### Generic raw attribute

#### Extension: <span class="nowrap">`raw_attribute`</span>

Inline spans and fenced code blocks with a special kind of attribute
will be parsed as raw content with the designated format. For example,
the following produces a raw roff <span class="nowrap">`ms`</span>
block:

    ```{=ms}
    .MYMACRO
    blah blah
    ```

And the following produces a raw <span class="nowrap">`html`</span>
inline element:

    This is `<a>html</a>`{=html}

This can be useful to insert raw xml into <span
class="nowrap">`docx`</span> documents, e.g. a pagebreak:

    ```{=openxml}
    <w:p>
      <w:r>
        <w:br w:type="page"/>
      </w:r>
    </w:p>
    ```

The format name should match the target format name (see [<span
class="nowrap">`-t/--to`</span>](#option--to){.option}, above, for a
list, or use <span
class="nowrap">`pandoc --list-output-formats`</span>). Use <span
class="nowrap">`openxml`</span> for <span class="nowrap">`docx`</span>
output, <span class="nowrap">`opendocument`</span> for <span
class="nowrap">`odt`</span> output, <span class="nowrap">`html5`</span>
for <span class="nowrap">`epub3`</span> output, <span
class="nowrap">`html4`</span> for <span class="nowrap">`epub2`</span>
output, and <span class="nowrap">`latex`</span>, <span
class="nowrap">`beamer`</span>, <span class="nowrap">`ms`</span>, or
<span class="nowrap">`html5`</span> for <span
class="nowrap">`pdf`</span> output (depending on what you use for [<span
class="nowrap">`--pdf-engine`</span>](#option--pdf-engine){.option}).

This extension presupposes that the relevant kind of inline code or
fenced code block is enabled. Thus, for example, to use a raw attribute
with a backtick code block, <span
class="nowrap">`backtick_code_blocks`</span> must be enabled.

The raw attribute cannot be combined with regular attributes.

LaTeX macros
------------

#### Extension: <span class="nowrap">`latex_macros`</span>

When this extension is enabled, pandoc will parse LaTeX macro
definitions and apply the resulting macros to all LaTeX math and raw
LaTeX. So, for example, the following will work in all output formats,
not just LaTeX:

    \newcommand{\tuple}[1]{\langle #1 \rangle}

    $\tuple{a, b, c}$

Note that LaTeX macros will not be applied if they occur inside a raw
span or block marked with the [<span
class="nowrap">`raw_attribute`</span>
extension](#extension-raw_attribute).

When <span class="nowrap">`latex_macros`</span> is disabled, the raw
LaTeX and math will not have macros applied. This is usually a better
approach when you are targeting LaTeX or PDF.

Whether or not <span class="nowrap">`latex_macros`</span> is enabled,
the macro definitions will still be passed through as raw LaTeX.

Links
-----

Markdown allows links to be specified in several ways.

### Automatic links

If you enclose a URL or email address in pointy brackets, it will become
a link:

    <http://google.com>
    <sam@green.eggs.ham>

### Inline links

An inline link consists of the link text in square brackets, followed by
the URL in parentheses. (Optionally, the URL can be followed by a link
title, in quotes.)

    This is an [inline link](/url), and here's [one with
    a title](http://fsf.org "click here for a good time!").

There can be no space between the bracketed part and the parenthesized
part. The link text can contain formatting (such as emphasis), but the
title cannot.

Email addresses in inline links are not autodetected, so they have to be
prefixed with <span class="nowrap">`mailto`</span>:

    [Write me!](mailto:sam@green.eggs.ham)

### Reference links

An *explicit* reference link has two parts, the link itself and the link
definition, which may occur elsewhere in the document (either before or
after the link).

The link consists of link text in square brackets, followed by a label
in square brackets. (There cannot be space between the two unless the
<span class="nowrap">`spaced_reference_links`</span> extension is
enabled.) The link definition consists of the bracketed label, followed
by a colon and a space, followed by the URL, and optionally (after a
space) a link title either in quotes or in parentheses. The label must
not be parseable as a citation (assuming the <span
class="nowrap">`citations`</span> extension is enabled): citations take
precedence over link labels.

Here are some examples:

    [my label 1]: /foo/bar.html  "My title, optional"
    [my label 2]: /foo
    [my label 3]: http://fsf.org (The free software foundation)
    [my label 4]: /bar#special  'A title in single quotes'

The URL may optionally be surrounded by angle brackets:

    [my label 5]: <http://foo.bar.baz>

The title may go on the next line:

    [my label 3]: http://fsf.org
      "The free software foundation"

Note that link labels are not case sensitive. So, this will work:

    Here is [my link][FOO]

    [Foo]: /bar/baz

In an *implicit* reference link, the second pair of brackets is empty:

    See [my website][].

    [my website]: http://foo.bar.baz

Note: In <span class="nowrap">`Markdown.pl`</span> and most other
Markdown implementations, reference link definitions cannot occur in
nested constructions such as list items or block quotes. Pandoc lifts
this arbitrary seeming restriction. So the following is fine in pandoc,
though not in most other implementations:

    > My block [quote].
    >
    > [quote]: /foo

#### Extension: <span class="nowrap">`shortcut_reference_links`</span>

In a *shortcut* reference link, the second pair of brackets may be
omitted entirely:

    See [my website].

    [my website]: http://foo.bar.baz

### Internal links

To link to another section of the same document, use the automatically
generated identifier (see [Heading identifiers](#heading-identifiers)).
For example:

    See the [Introduction](#introduction).

or

    See the [Introduction].

    [Introduction]: #introduction

Internal links are currently supported for HTML formats (including HTML
slide shows and EPUB), LaTeX, and ConTeXt.

Images
------

A link immediately preceded by a <span class="nowrap">`!`</span> will be
treated as an image. The link text will be used as the image’s alt text:

    ![la lune](lalune.jpg "Voyage to the moon")

    ![movie reel]

    [movie reel]: movie.gif

#### Extension: <span class="nowrap">`implicit_figures`</span>

An image with nonempty alt text, occurring by itself in a paragraph,
will be rendered as a figure with a caption. The image’s alt text will
be used as the caption.

    ![This is the caption](/url/of/image.png)

How this is rendered depends on the output format. Some output formats
(e.g. RTF) do not yet support figures. In those formats, you’ll just get
an image in a paragraph by itself, with no caption.

If you just want a regular inline image, just make sure it is not the
only thing in the paragraph. One way to do this is to insert a
nonbreaking space after the image:

    ![This image won't be a figure](/url/of/image.png)\

Note that in reveal.js slide shows, an image in a paragraph by itself
that has the <span class="nowrap">`stretch`</span> class will fill the
screen, and the caption and figure tags will be omitted.

#### Extension: <span class="nowrap">`link_attributes`</span>

Attributes can be set on links and images:

    An inline ![image](foo.jpg){#id .class width=30 height=20px}
    and a reference ![image][ref] with attributes.

    [ref]: foo.jpg "optional title" {#id .class key=val key2="val 2"}

(This syntax is compatible with [PHP Markdown
Extra](https://michelf.ca/projects/php-markdown/extra/) when only <span
class="nowrap">`#id`</span> and <span class="nowrap">`.class`</span> are
used.)

For HTML and EPUB, all attributes except <span
class="nowrap">`width`</span> and <span class="nowrap">`height`</span>
(but including <span class="nowrap">`srcset`</span> and <span
class="nowrap">`sizes`</span>) are passed through as is. The other
writers ignore attributes that are not supported by their output format.

The <span class="nowrap">`width`</span> and <span
class="nowrap">`height`</span> attributes on images are treated
specially. When used without a unit, the unit is assumed to be pixels.
However, any of the following unit identifiers can be used: <span
class="nowrap">`px`</span>, <span class="nowrap">`cm`</span>, <span
class="nowrap">`mm`</span>, <span class="nowrap">`in`</span>, <span
class="nowrap">`inch`</span> and <span class="nowrap">`%`</span>. There
must not be any spaces between the number and the unit. For example:

    ![](file.jpg){ width=50% }

-   Dimensions are converted to inches for output in page-based formats
    like LaTeX. Dimensions are converted to pixels for output in
    HTML-like formats. Use the [<span
    class="nowrap">`--dpi`</span>](#option--dpi){.option} option to
    specify the number of pixels per inch. The default is 96dpi.
-   The <span class="nowrap">`%`</span> unit is generally relative to
    some available space. For example the above example will render to
    the following.
    -   HTML: <span
        class="nowrap">`<img href="file.jpg" style="width: 50%;" />`</span>
    -   LaTeX: <span
        class="nowrap">`\includegraphics[width=0.5\textwidth,height=\textheight]{file.jpg}`</span>
        (If you’re using a custom template, you need to configure <span
        class="nowrap">`graphicx`</span> as in the default template.)
    -   ConTeXt: <span
        class="nowrap">`\externalfigure[file.jpg][width=0.5\textwidth]`</span>
-   Some output formats have a notion of a class
    ([ConTeXt](http://wiki.contextgarden.net/Using_Graphics#Multiple_Image_Settings))
    or a unique identifier (LaTeX <span
    class="nowrap">`\caption`</span>), or both (HTML).
-   When no <span class="nowrap">`width`</span> or <span
    class="nowrap">`height`</span> attributes are specified, the
    fallback is to look at the image resolution and the dpi metadata
    embedded in the image file.

Divs and Spans
--------------

Using the <span class="nowrap">`native_divs`</span> and <span
class="nowrap">`native_spans`</span> extensions (see
[above](#extension-native_divs)), HTML syntax can be used as part of
markdown to create native <span class="nowrap">`Div`</span> and <span
class="nowrap">`Span`</span> elements in the pandoc AST (as opposed to
raw HTML). However, there is also nicer syntax available:

#### Extension: <span class="nowrap">`fenced_divs`</span>

Allow special fenced syntax for native <span class="nowrap">`Div`</span>
blocks. A Div starts with a fence containing at least three consecutive
colons plus some attributes. The attributes may optionally be followed
by another string of consecutive colons. The attribute syntax is exactly
as in fenced code blocks (see [Extension: <span
class="nowrap">`fenced_code_attributes`</span>](#extension-fenced_code_attributes)).
As with fenced code blocks, one can use either attributes in curly
braces or a single unbraced word, which will be treated as a class name.
The Div ends with another line containing a string of at least three
consecutive colons. The fenced Div should be separated by blank lines
from preceding and following blocks.

Example:

    ::::: {#special .sidebar}
    Here is a paragraph.

    And another.
    :::::

Fenced divs can be nested. Opening fences are distinguished because they
*must* have attributes:

    ::: Warning ::::::
    This is a warning.

    ::: Danger
    This is a warning within a warning.
    :::
    ::::::::::::::::::

Fences without attributes are always closing fences. Unlike with fenced
code blocks, the number of colons in the closing fence need not match
the number in the opening fence. However, it can be helpful for visual
clarity to use fences of different lengths to distinguish nested divs
from their parents.

#### Extension: <span class="nowrap">`bracketed_spans`</span>

A bracketed sequence of inlines, as one would use to begin a link, will
be treated as a <span class="nowrap">`Span`</span> with attributes if it
is followed immediately by attributes:

    [This is *some text*]{.class key="val"}

Footnotes
---------

#### Extension: <span class="nowrap">`footnotes`</span>

Pandoc’s Markdown allows footnotes, using the following syntax:

    Here is a footnote reference,[^1] and another.[^longnote]

    [^1]: Here is the footnote.

    [^longnote]: Here's one with multiple blocks.

        Subsequent paragraphs are indented to show that they
    belong to the previous footnote.

            { some.code }

        The whole paragraph can be indented, or just the first
        line.  In this way, multi-paragraph footnotes work like
        multi-paragraph list items.

    This paragraph won't be part of the note, because it
    isn't indented.

The identifiers in footnote references may not contain spaces, tabs, or
newlines. These identifiers are used only to correlate the footnote
reference with the note itself; in the output, footnotes will be
numbered sequentially.

The footnotes themselves need not be placed at the end of the document.
They may appear anywhere except inside other block elements (lists,
block quotes, tables, etc.). Each footnote should be separated from
surrounding content (including other footnotes) by blank lines.

#### Extension: <span class="nowrap">`inline_notes`</span>

Inline footnotes are also allowed (though, unlike regular notes, they
cannot contain multiple paragraphs). The syntax is as follows:

    Here is an inline note.^[Inlines notes are easier to write, since
    you don't have to pick an identifier and move down to type the
    note.]

Inline and regular footnotes may be mixed freely.

Citations
---------

#### Extension: <span class="nowrap">`citations`</span> {#extension-citations}

Using an external filter, <span class="nowrap">`pandoc-citeproc`</span>,
pandoc can automatically generate citations and a bibliography in a
number of styles. Basic usage is

    pandoc --filter pandoc-citeproc myinput.txt

In order to use this feature, you will need to specify a bibliography
file using the <span class="nowrap">`bibliography`</span> metadata field
in a YAML metadata section, or [<span
class="nowrap">`--bibliography`</span>](#option--bibliography){.option}
command line argument. You can supply multiple [<span
class="nowrap">`--bibliography`</span>](#option--bibliography){.option}
arguments or set <span class="nowrap">`bibliography`</span> metadata
field to YAML array, if you want to use multiple bibliography files. The
bibliography may have any of these formats:

  Format        File extension
  ------------- ----------------
  BibLaTeX      .bib
  BibTeX        .bibtex
  Copac         .copac
  CSL JSON      .json
  CSL YAML      .yaml
  EndNote       .enl
  EndNote XML   .xml
  ISI           .wos
  MEDLINE       .medline
  MODS          .mods
  RIS           .ris

Note that <span class="nowrap">`.bib`</span> can be used with both
BibTeX and BibLaTeX files; use <span class="nowrap">`.bibtex`</span> to
force BibTeX.

Note that <span class="nowrap">`pandoc-citeproc --bib2json`</span> and
<span class="nowrap">`pandoc-citeproc --bib2yaml`</span> can produce
<span class="nowrap">`.json`</span> and <span
class="nowrap">`.yaml`</span> files from any of the supported formats.

In-field markup: In BibTeX and BibLaTeX databases, pandoc-citeproc
parses a subset of LaTeX markup; in CSL YAML databases, pandoc Markdown;
and in CSL JSON databases, an [HTML-like
markup](http://docs.citationstyles.org/en/1.0/release-notes.html#rich-text-markup-within-fields):

<span class="nowrap">`<i>...</i>`</span>
:   italics

<span class="nowrap">`<b>...</b>`</span>
:   bold

<span class="nowrap">`<span style="font-variant:small-caps;">...</span>`</span> or <span class="nowrap">`<sc>...</sc>`</span>
:   small capitals

<span class="nowrap">`<sub>...</sub>`</span>
:   subscript

<span class="nowrap">`<sup>...</sup>`</span>
:   superscript

<span class="nowrap">`<span class="nocase">...</span>`</span>
:   prevent a phrase from being capitalized as title case

<span class="nowrap">`pandoc-citeproc -j`</span> and <span
class="nowrap">`-y`</span> interconvert the CSL JSON and CSL YAML
formats as far as possible.

As an alternative to specifying a bibliography file using [<span
class="nowrap">`--bibliography`</span>](#option--bibliography){.option}
or the YAML metadata field <span class="nowrap">`bibliography`</span>,
you can include the citation data directly in the <span
class="nowrap">`references`</span> field of the document’s YAML
metadata. The field should contain an array of YAML-encoded references,
for example:

    ---
    references:
    - type: article-journal
      id: WatsonCrick1953
      author:
      - family: Watson
        given: J. D.
      - family: Crick
        given: F. H. C.
      issued:
        date-parts:
        - - 1953
          - 4
          - 25
      title: 'Molecular structure of nucleic acids: a structure for deoxyribose
        nucleic acid'
      title-short: Molecular structure of nucleic acids
      container-title: Nature
      volume: 171
      issue: 4356
      page: 737-738
      DOI: 10.1038/171737a0
      URL: http://www.nature.com/nature/journal/v171/n4356/abs/171737a0.html
      language: en-GB
    ...

(<span class="nowrap">`pandoc-citeproc --bib2yaml`</span> can produce
these from a bibliography file in one of the supported formats.)

Citations and references can be formatted using any style supported by
the [Citation Style Language](http://citationstyles.org), listed in the
[Zotero Style Repository](https://www.zotero.org/styles). These files
are specified using the [<span
class="nowrap">`--csl`</span>](#option--csl){.option} option or the
<span class="nowrap">`csl`</span> metadata field. By default, <span
class="nowrap">`pandoc-citeproc`</span> will use the [Chicago Manual of
Style](http://chicagomanualofstyle.org) author-date format. The CSL
project provides further information on [finding and editing
styles](https://citationstyles.org/authors/).

To make your citations hyperlinks to the corresponding bibliography
entries, add <span class="nowrap">`link-citations: true`</span> to your
YAML metadata.

Citations go inside square brackets and are separated by semicolons.
Each citation must have a key, composed of ‘@’ + the citation identifier
from the database, and may optionally have a prefix, a locator, and a
suffix. The citation key must begin with a letter, digit, or <span
class="nowrap">`_`</span>, and may contain alphanumerics, <span
class="nowrap">`_`</span>, and internal punctuation characters (<span
class="nowrap">`:.#$%&-+?<>~/`</span>). Here are some examples:

    Blah blah [see @doe99, pp. 33-35; also @smith04, chap. 1].

    Blah blah [@doe99, pp. 33-35, 38-39 and *passim*].

    Blah blah [@smith04; @doe99].

<span class="nowrap">`pandoc-citeproc`</span> detects locator terms in
the [CSL locale
files](https://github.com/citation-style-language/locales). Either
abbreviated or unabbreviated forms are accepted. In the <span
class="nowrap">`en-US`</span> locale, locator terms can be written in
either singular or plural forms, as <span class="nowrap">`book`</span>,
<span class="nowrap">`bk.`</span>/<span class="nowrap">`bks.`</span>;
<span class="nowrap">`chapter`</span>, <span
class="nowrap">`chap.`</span>/<span class="nowrap">`chaps.`</span>;
<span class="nowrap">`column`</span>, <span
class="nowrap">`col.`</span>/<span class="nowrap">`cols.`</span>; <span
class="nowrap">`figure`</span>, <span class="nowrap">`fig.`</span>/<span
class="nowrap">`figs.`</span>; <span class="nowrap">`folio`</span>,
<span class="nowrap">`fol.`</span>/<span class="nowrap">`fols.`</span>;
<span class="nowrap">`number`</span>, <span
class="nowrap">`no.`</span>/<span class="nowrap">`nos.`</span>; <span
class="nowrap">`line`</span>, <span class="nowrap">`l.`</span>/<span
class="nowrap">`ll.`</span>; <span class="nowrap">`note`</span>, <span
class="nowrap">`n.`</span>/<span class="nowrap">`nn.`</span>; <span
class="nowrap">`opus`</span>, <span class="nowrap">`op.`</span>/<span
class="nowrap">`opp.`</span>; <span class="nowrap">`page`</span>, <span
class="nowrap">`p.`</span>/<span class="nowrap">`pp.`</span>; <span
class="nowrap">`paragraph`</span>, <span
class="nowrap">`para.`</span>/<span class="nowrap">`paras.`</span>;
<span class="nowrap">`part`</span>, <span
class="nowrap">`pt.`</span>/<span class="nowrap">`pts.`</span>; <span
class="nowrap">`section`</span>, <span
class="nowrap">`sec.`</span>/<span class="nowrap">`secs.`</span>; <span
class="nowrap">`sub verbo`</span>, <span
class="nowrap">`s.v.`</span>/<span class="nowrap">`s.vv.`</span>; <span
class="nowrap">`verse`</span>, <span class="nowrap">`v.`</span>/<span
class="nowrap">`vv.`</span>; <span class="nowrap">`volume`</span>, <span
class="nowrap">`vol.`</span>/<span class="nowrap">`vols.`</span>; <span
class="nowrap">`¶`</span>/<span class="nowrap">`¶¶`</span>; <span
class="nowrap">`§`</span>/<span class="nowrap">`§§`</span>. If no
locator term is used, “page” is assumed.

<span class="nowrap">`pandoc-citeproc`</span> will use heuristics to
distinguish the locator from the suffix. In complex cases, the locator
can be enclosed in curly braces (using <span
class="nowrap">`pandoc-citeproc`</span> 0.15 and higher only):

    [@smith{ii, A, D-Z}, with a suffix]
    [@smith, {pp. iv, vi-xi, (xv)-(xvii)} with suffix here]

A minus sign (<span class="nowrap">`-`</span>) before the <span
class="nowrap">`@`</span> will suppress mention of the author in the
citation. This can be useful when the author is already mentioned in the
text:

    Smith says blah [-@smith04].

You can also write an in-text citation, as follows:

    @smith04 says blah.

    @smith04 [p. 33] says blah.

If the style calls for a list of works cited, it will be placed in a div
with id <span class="nowrap">`refs`</span>, if one exists:

    ::: {#refs}
    :::

Otherwise, it will be placed at the end of the document. Generation of
the bibliography can be suppressed by setting <span
class="nowrap">`suppress-bibliography: true`</span> in the YAML
metadata.

If you wish the bibliography to have a section heading, you can set
<span class="nowrap">`reference-section-title`</span> in the metadata,
or put the heading at the beginning of the div with id <span
class="nowrap">`refs`</span> (if you are using it) or at the end of your
document:

    last paragraph...

    # References

The bibliography will be inserted after this heading. Note that the
<span class="nowrap">`unnumbered`</span> class will be added to this
heading, so that the section will not be numbered.

If you want to include items in the bibliography without actually citing
them in the body text, you can define a dummy <span
class="nowrap">`nocite`</span> metadata field and put the citations
there:

    ---
    nocite: |
      @item1, @item2
    ...

    @item3

In this example, the document will contain a citation for <span
class="nowrap">`item3`</span> only, but the bibliography will contain
entries for <span class="nowrap">`item1`</span>, <span
class="nowrap">`item2`</span>, and <span class="nowrap">`item3`</span>.

It is possible to create a bibliography with all the citations, whether
or not they appear in the document, by using a wildcard:

    ---
    nocite: |
      @*
    ...

For LaTeX output, you can also use [<span
class="nowrap">`natbib`</span>](https://ctan.org/pkg/natbib) or [<span
class="nowrap">`biblatex`</span>](https://ctan.org/pkg/biblatex) to
render the bibliography. In order to do so, specify bibliography files
as outlined above, and add [<span
class="nowrap">`--natbib`</span>](#option--natbib){.option} or [<span
class="nowrap">`--biblatex`</span>](#option--biblatex){.option} argument
to <span class="nowrap">`pandoc`</span> invocation. Bear in mind that
bibliography files have to be in respective format (either BibTeX or
BibLaTeX).

For more information, see the [pandoc-citeproc man
page](https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md).

Non-pandoc extensions
---------------------

The following Markdown syntax extensions are not enabled by default in
pandoc, but may be enabled by adding <span
class="nowrap">`+EXTENSION`</span> to the format name, where <span
class="nowrap">`EXTENSION`</span> is the name of the extension. Thus,
for example, <span class="nowrap">`markdown+hard_line_breaks`</span> is
Markdown with hard line breaks.

#### Extension: <span class="nowrap">`old_dashes`</span>

Selects the pandoc &lt;= 1.8.2.1 behavior for parsing smart dashes:
<span class="nowrap">`-`</span> before a numeral is an en-dash, and
<span class="nowrap">`--`</span> is an em-dash. This option only has an
effect if <span class="nowrap">`smart`</span> is enabled. It is selected
automatically for <span class="nowrap">`textile`</span> input.

#### Extension: <span class="nowrap">`angle_brackets_escapable`</span>

Allow <span class="nowrap">`<`</span> and <span
class="nowrap">`>`</span> to be backslash-escaped, as they can be in
GitHub flavored Markdown but not original Markdown. This is implied by
pandoc’s default <span class="nowrap">`all_symbols_escapable`</span>.

#### Extension: <span class="nowrap">`lists_without_preceding_blankline`</span>

Allow a list to occur right after a paragraph, with no intervening blank
space.

#### Extension: <span class="nowrap">`four_space_rule`</span>

Selects the pandoc &lt;= 2.0 behavior for parsing lists, so that four
spaces indent are needed for list item continuation paragraphs.

#### Extension: <span class="nowrap">`spaced_reference_links`</span>

Allow whitespace between the two components of a reference link, for
example,

    [foo] [bar].

#### Extension: <span class="nowrap">`hard_line_breaks`</span>

Causes all newlines within a paragraph to be interpreted as hard line
breaks instead of spaces.

#### Extension: <span class="nowrap">`ignore_line_breaks`</span>

Causes newlines within a paragraph to be ignored, rather than being
treated as spaces or as hard line breaks. This option is intended for
use with East Asian languages where spaces are not used between words,
but text is divided into lines for readability.

#### Extension: <span class="nowrap">`east_asian_line_breaks`</span>

Causes newlines within a paragraph to be ignored, rather than being
treated as spaces or as hard line breaks, when they occur between two
East Asian wide characters. This is a better choice than <span
class="nowrap">`ignore_line_breaks`</span> for texts that include a mix
of East Asian wide characters and other characters.

#### Extension: <span class="nowrap">`emoji`</span>

Parses textual emojis like <span class="nowrap">`:smile:`</span> as
Unicode emoticons.

#### Extension: <span class="nowrap">`tex_math_single_backslash`</span>

Causes anything between <span class="nowrap">`\(`</span> and <span
class="nowrap">`\)`</span> to be interpreted as inline TeX math, and
anything between <span class="nowrap">`\[`</span> and <span
class="nowrap">`\]`</span> to be interpreted as display TeX math. Note:
a drawback of this extension is that it precludes escaping <span
class="nowrap">`(`</span> and <span class="nowrap">`[`</span>.

#### Extension: <span class="nowrap">`tex_math_double_backslash`</span>

Causes anything between <span class="nowrap">`\\(`</span> and <span
class="nowrap">`\\)`</span> to be interpreted as inline TeX math, and
anything between <span class="nowrap">`\\[`</span> and <span
class="nowrap">`\\]`</span> to be interpreted as display TeX math.

#### Extension: <span class="nowrap">`markdown_attribute`</span>

By default, pandoc interprets material inside block-level tags as
Markdown. This extension changes the behavior so that Markdown is only
parsed inside block-level tags if the tags have the attribute <span
class="nowrap">`markdown=1`</span>.

#### Extension: <span class="nowrap">`mmd_title_block`</span>

Enables a [MultiMarkdown](http://fletcherpenney.net/multimarkdown/)
style title block at the top of the document, for example:

    Title:   My title
    Author:  John Doe
    Date:    September 1, 2008
    Comment: This is a sample mmd title block, with
             a field spanning multiple lines.

See the MultiMarkdown documentation for details. If <span
class="nowrap">`pandoc_title_block`</span> or <span
class="nowrap">`yaml_metadata_block`</span> is enabled, it will take
precedence over <span class="nowrap">`mmd_title_block`</span>.

#### Extension: <span class="nowrap">`abbreviations`</span>

Parses PHP Markdown Extra abbreviation keys, like

    *[HTML]: Hypertext Markup Language

Note that the pandoc document model does not support abbreviations, so
if this extension is enabled, abbreviation keys are simply skipped (as
opposed to being parsed as paragraphs).

#### Extension: <span class="nowrap">`autolink_bare_uris`</span>

Makes all absolute URIs into links, even when not surrounded by pointy
braces <span class="nowrap">`<...>`</span>.

#### Extension: <span class="nowrap">`mmd_link_attributes`</span>

Parses multimarkdown style key-value attributes on link and image
references. This extension should not be confused with the [<span
class="nowrap">`link_attributes`</span>](#extension-link_attributes)
extension.

    This is a reference ![image][ref] with multimarkdown attributes.

    [ref]: http://path.to/image "Image title" width=20px height=30px
           id=myId class="myClass1 myClass2"

#### Extension: <span class="nowrap">`mmd_header_identifiers`</span>

Parses multimarkdown style heading identifiers (in square brackets,
after the heading but before any trailing <span
class="nowrap">`#`</span>s in an ATX heading).

#### Extension: <span class="nowrap">`compact_definition_lists`</span>

Activates the definition list syntax of pandoc 1.12.x and earlier. This
syntax differs from the one described above under [Definition
lists](#definition-lists) in several respects:

-   No blank line is required between consecutive items of the
    definition list.
-   To get a “tight” or “compact” list, omit space between consecutive
    items; the space between a term and its definition does not
    affect anything.
-   Lazy wrapping of paragraphs is not allowed: the entire definition
    must be indented four spaces.[^4^](#fn4){#fnref4 .footnote-ref}

Markdown variants
-----------------

In addition to pandoc’s extended Markdown, the following Markdown
variants are supported:

<span class="nowrap">`markdown_phpextra`</span> (PHP Markdown Extra)
:   <span class="nowrap">`footnotes`</span>, <span
    class="nowrap">`pipe_tables`</span>, <span
    class="nowrap">`raw_html`</span>, <span
    class="nowrap">`markdown_attribute`</span>, <span
    class="nowrap">`fenced_code_blocks`</span>, <span
    class="nowrap">`definition_lists`</span>, <span
    class="nowrap">`intraword_underscores`</span>, <span
    class="nowrap">`header_attributes`</span>, <span
    class="nowrap">`link_attributes`</span>, <span
    class="nowrap">`abbreviations`</span>, <span
    class="nowrap">`shortcut_reference_links`</span>, <span
    class="nowrap">`spaced_reference_links`</span>.

<span class="nowrap">`markdown_github`</span> (deprecated GitHub-Flavored Markdown)
:   <span class="nowrap">`pipe_tables`</span>, <span
    class="nowrap">`raw_html`</span>, <span
    class="nowrap">`fenced_code_blocks`</span>, <span
    class="nowrap">`auto_identifiers`</span>, <span
    class="nowrap">`gfm_auto_identifiers`</span>, <span
    class="nowrap">`backtick_code_blocks`</span>, <span
    class="nowrap">`autolink_bare_uris`</span>, <span
    class="nowrap">`space_in_atx_header`</span>, <span
    class="nowrap">`intraword_underscores`</span>, <span
    class="nowrap">`strikeout`</span>, <span
    class="nowrap">`task_lists`</span>, <span
    class="nowrap">`emoji`</span>, <span
    class="nowrap">`shortcut_reference_links`</span>, <span
    class="nowrap">`angle_brackets_escapable`</span>, <span
    class="nowrap">`lists_without_preceding_blankline`</span>.

<span class="nowrap">`markdown_mmd`</span> (MultiMarkdown)
:   <span class="nowrap">`pipe_tables`</span>, <span
    class="nowrap">`raw_html`</span>, <span
    class="nowrap">`markdown_attribute`</span>, <span
    class="nowrap">`mmd_link_attributes`</span>, <span
    class="nowrap">`tex_math_double_backslash`</span>, <span
    class="nowrap">`intraword_underscores`</span>, <span
    class="nowrap">`mmd_title_block`</span>, <span
    class="nowrap">`footnotes`</span>, <span
    class="nowrap">`definition_lists`</span>, <span
    class="nowrap">`all_symbols_escapable`</span>, <span
    class="nowrap">`implicit_header_references`</span>, <span
    class="nowrap">`auto_identifiers`</span>, <span
    class="nowrap">`mmd_header_identifiers`</span>, <span
    class="nowrap">`shortcut_reference_links`</span>, <span
    class="nowrap">`implicit_figures`</span>, <span
    class="nowrap">`superscript`</span>, <span
    class="nowrap">`subscript`</span>, <span
    class="nowrap">`backtick_code_blocks`</span>, <span
    class="nowrap">`spaced_reference_links`</span>, <span
    class="nowrap">`raw_attribute`</span>.

<span class="nowrap">`markdown_strict`</span> (Markdown.pl)
:   <span class="nowrap">`raw_html`</span>, <span
    class="nowrap">`shortcut_reference_links`</span>, <span
    class="nowrap">`spaced_reference_links`</span>.

We also support <span class="nowrap">`commonmark`</span> and <span
class="nowrap">`gfm`</span> (GitHub-Flavored Markdown, which is
implemented as a set of extensions on <span
class="nowrap">`commonmark`</span>).

Note, however, that <span class="nowrap">`commonmark`</span> and <span
class="nowrap">`gfm`</span> have limited support for extensions. Only
those listed below (and <span class="nowrap">`smart`</span>, <span
class="nowrap">`raw_tex`</span>, and <span
class="nowrap">`hard_line_breaks`</span>) will work. The extensions can,
however, all be individually disabled. Also, <span
class="nowrap">`raw_tex`</span> only affects <span
class="nowrap">`gfm`</span> output, not input.

<span class="nowrap">`gfm`</span> (GitHub-Flavored Markdown)
:   <span class="nowrap">`pipe_tables`</span>, <span
    class="nowrap">`raw_html`</span>, <span
    class="nowrap">`fenced_code_blocks`</span>, <span
    class="nowrap">`auto_identifiers`</span>, <span
    class="nowrap">`gfm_auto_identifiers`</span>, <span
    class="nowrap">`backtick_code_blocks`</span>, <span
    class="nowrap">`autolink_bare_uris`</span>, <span
    class="nowrap">`space_in_atx_header`</span>, <span
    class="nowrap">`intraword_underscores`</span>, <span
    class="nowrap">`strikeout`</span>, <span
    class="nowrap">`task_lists`</span>, <span
    class="nowrap">`emoji`</span>, <span
    class="nowrap">`shortcut_reference_links`</span>, <span
    class="nowrap">`angle_brackets_escapable`</span>, <span
    class="nowrap">`lists_without_preceding_blankline`</span>.

Producing slide shows with pandoc
=================================

You can use pandoc to produce an HTML + JavaScript slide presentation
that can be viewed via a web browser. There are five ways to do this,
using [S5](http://meyerweb.com/eric/tools/s5/),
[DZSlides](http://paulrouget.com/dzslides/),
[Slidy](http://www.w3.org/Talks/Tools/Slidy/),
[Slideous](http://goessner.net/articles/slideous/), or
[reveal.js](http://lab.hakim.se/reveal-js/). You can also produce a PDF
slide show using LaTeX [<span
class="nowrap">`beamer`</span>](https://ctan.org/pkg/beamer), or slides
shows in Microsoft
[PowerPoint](https://en.wikipedia.org/wiki/Microsoft_PowerPoint) format.

Here’s the Markdown source for a simple slide show, <span
class="nowrap">`habits.txt`</span>:

    % Habits
    % John Doe
    % March 22, 2005

    # In the morning

    ## Getting up

    - Turn off alarm
    - Get out of bed

    ## Breakfast

    - Eat eggs
    - Drink coffee

    # In the evening

    ## Dinner

    - Eat spaghetti
    - Drink wine

    ------------------

    ![picture of spaghetti](images/spaghetti.jpg)

    ## Going to sleep

    - Get in bed
    - Count sheep

To produce an HTML/JavaScript slide show, simply type

    pandoc -t FORMAT -s habits.txt -o habits.html

where <span class="nowrap">`FORMAT`</span> is either <span
class="nowrap">`s5`</span>, <span class="nowrap">`slidy`</span>, <span
class="nowrap">`slideous`</span>, <span
class="nowrap">`dzslides`</span>, or <span
class="nowrap">`revealjs`</span>.

For Slidy, Slideous, reveal.js, and S5, the file produced by pandoc with
the [<span
class="nowrap">`-s/--standalone`</span>](#option--standalone){.option}
option embeds a link to JavaScript and CSS files, which are assumed to
be available at the relative path <span
class="nowrap">`s5/default`</span> (for S5), <span
class="nowrap">`slideous`</span> (for Slideous), <span
class="nowrap">`reveal.js`</span> (for reveal.js), or at the Slidy
website at <span class="nowrap">`w3.org`</span> (for Slidy). (These
paths can be changed by setting the <span
class="nowrap">`slidy-url`</span>, <span
class="nowrap">`slideous-url`</span>, <span
class="nowrap">`revealjs-url`</span>, or <span
class="nowrap">`s5-url`</span> variables; see [Variables for HTML
slides](#variables-for-html-slides), above.) For DZSlides, the
(relatively short) JavaScript and CSS are included in the file by
default.

With all HTML slide formats, the [<span
class="nowrap">`--self-contained`</span>](#option--self-contained){.option}
option can be used to produce a single file that contains all of the
data necessary to display the slide show, including linked scripts,
stylesheets, images, and videos.

To produce a PDF slide show using beamer, type

    pandoc -t beamer habits.txt -o habits.pdf

Note that a reveal.js slide show can also be converted to a PDF by
printing it to a file from the browser.

To produce a Powerpoint slide show, type

    pandoc habits.txt -o habits.pptx

Structuring the slide show
--------------------------

By default, the *slide level* is the highest heading level in the
hierarchy that is followed immediately by content, and not another
heading, somewhere in the document. In the example above, level-1
headings are always followed by level-2 headings, which are followed by
content, so the slide level is 2. This default can be overridden using
the [<span
class="nowrap">`--slide-level`</span>](#option--slide-level){.option}
option.

The document is carved up into slides according to the following rules:

-   A horizontal rule always starts a new slide.

-   A heading at the slide level always starts a new slide.

-   Headings *below* the slide level in the hierarchy create headings
    *within* a slide.

-   Headings *above* the slide level in the hierarchy create “title
    slides,” which just contain the section title and help to break the
    slide show into sections. Non-slide content under these headings
    will be included on the title slide (for HTML slide shows) or in a
    subsequent slide with the same title (for beamer).

-   A title page is constructed automatically from the document’s title
    block, if present. (In the case of beamer, this can be disabled by
    commenting out some lines in the default template.)

These rules are designed to support many different styles of slide show.
If you don’t care about structuring your slides into sections and
subsections, you can just use level-1 headings for all each slide. (In
that case, level-1 will be the slide level.) But you can also structure
the slide show into sections, as in the example above.

Note: in reveal.js slide shows, if slide level is 2, a two-dimensional
layout will be produced, with level-1 headings building horizontally and
level-2 headings building vertically. It is not recommended that you use
deeper nesting of section levels with reveal.js.

Incremental lists
-----------------

By default, these writers produce lists that display “all at once.” If
you want your lists to display incrementally (one item at a time), use
the [<span class="nowrap">`-i`</span>](#option--incremental){.option}
option. If you want a particular list to depart from the default, put it
in a <span class="nowrap">`div`</span> block with class <span
class="nowrap">`incremental`</span> or <span
class="nowrap">`nonincremental`</span>. So, for example, using the <span
class="nowrap">`fenced div`</span> syntax, the following would be
incremental regardless of the document default:

    ::: incremental

    - Eat spaghetti
    - Drink wine

    :::

or

    ::: nonincremental

    - Eat spaghetti
    - Drink wine

    :::

While using <span class="nowrap">`incremental`</span> and <span
class="nowrap">`nonincremental`</span> divs are the recommended method
of setting incremental lists on a per-case basis, an older method is
also supported: putting lists inside a blockquote will depart from the
document default (that is, it will display incrementally without the
[<span class="nowrap">`-i`</span>](#option--incremental){.option} option
and all at once with the [<span
class="nowrap">`-i`</span>](#option--incremental){.option} option):

    > - Eat spaghetti
    > - Drink wine

Both methods allow incremental and nonincremental lists to be mixed in a
single document.

Inserting pauses
----------------

You can add “pauses” within a slide by including a paragraph containing
three dots, separated by spaces:

    # Slide with a pause

    content before the pause

    . . .

    content after the pause

Styling the slides
------------------

You can change the style of HTML slides by putting customized CSS files
in <span class="nowrap">`$DATADIR/s5/default`</span> (for S5), <span
class="nowrap">`$DATADIR/slidy`</span> (for Slidy), or <span
class="nowrap">`$DATADIR/slideous`</span> (for Slideous), where <span
class="nowrap">`$DATADIR`</span> is the user data directory (see [<span
class="nowrap">`--data-dir`</span>](#option--data-dir){.option}, above).
The originals may be found in pandoc’s system data directory (generally
<span class="nowrap">`$CABALDIR/pandoc-VERSION/s5/default`</span>).
Pandoc will look there for any files it does not find in the user data
directory.

For dzslides, the CSS is included in the HTML file itself, and may be
modified there.

All [reveal.js configuration
options](https://github.com/hakimel/reveal.js#configuration) can be set
through variables. For example, themes can be used by setting the <span
class="nowrap">`theme`</span> variable:

    -V theme=moon

Or you can specify a custom stylesheet using the [<span
class="nowrap">`--css`</span>](#option--css){.option} option.

To style beamer slides, you can specify a <span
class="nowrap">`theme`</span>, <span class="nowrap">`colortheme`</span>,
<span class="nowrap">`fonttheme`</span>, <span
class="nowrap">`innertheme`</span>, and <span
class="nowrap">`outertheme`</span>, using the [<span
class="nowrap">`-V`</span>](#option--variable){.option} option:

    pandoc -t beamer habits.txt -V theme:Warsaw -o habits.pdf

Note that heading attributes will turn into slide attributes (on a <span
class="nowrap">`<div>`</span> or <span
class="nowrap">`<section>`</span>) in HTML slide formats, allowing you
to style individual slides. In beamer, the only heading attribute that
affects slides is the <span class="nowrap">`allowframebreaks`</span>
class, which sets the <span class="nowrap">`allowframebreaks`</span>
option, causing multiple slides to be created if the content overfills
the frame. This is recommended especially for bibliographies:

    # References {.allowframebreaks}

Speaker notes
-------------

Speaker notes are supported in reveal.js and PowerPoint (pptx) output.
You can add notes to your Markdown document thus:

    ::: notes

    This is my note.

    - It can contain Markdown
    - like this list

    :::

To show the notes window in reveal.js, press <span
class="nowrap">`s`</span> while viewing the presentation. Speaker notes
in PowerPoint will be available, as usual, in handouts and presenter
view.

Notes are not yet supported for other slide formats, but the notes will
not appear on the slides themselves.

Columns
-------

To put material in side by side columns, you can use a native div
container with class <span class="nowrap">`columns`</span>, containing
two or more div containers with class <span
class="nowrap">`column`</span> and a <span class="nowrap">`width`</span>
attribute:

    :::::::::::::: {.columns}
    ::: {.column width="40%"}
    contents...
    :::
    ::: {.column width="60%"}
    contents...
    :::
    ::::::::::::::

Frame attributes in beamer
--------------------------

Sometimes it is necessary to add the LaTeX <span
class="nowrap">`[fragile]`</span> option to a frame in beamer (for
example, when using the <span class="nowrap">`minted`</span>
environment). This can be forced by adding the <span
class="nowrap">`fragile`</span> class to the heading introducing the
slide:

    # Fragile slide {.fragile}

All of the other frame attributes described in Section 8.1 of the
[Beamer User’s
Guide](http://mirrors.ctan.org/macros/latex/contrib/beamer/doc/beameruserguide.pdf)
may also be used: <span class="nowrap">`allowdisplaybreaks`</span>,
<span class="nowrap">`allowframebreaks`</span>, <span
class="nowrap">`b`</span>, <span class="nowrap">`c`</span>, <span
class="nowrap">`t`</span>, <span class="nowrap">`environment`</span>,
<span class="nowrap">`label`</span>, <span
class="nowrap">`plain`</span>, <span class="nowrap">`shrink`</span>,
<span class="nowrap">`standout`</span>, <span
class="nowrap">`noframenumbering`</span>.

Background in reveal.js and beamer
----------------------------------

Background images can be added to self-contained reveal.js slideshows
and to beamer slideshows.

For the same image on every slide, use the configuration option <span
class="nowrap">`background-image`</span> either in the YAML metadata
block or as a command-line variable. (There are no other options in
beamer and the rest of this section concerns reveal.js slideshows.)

For reveal.js, you can instead use the reveal.js-native option <span
class="nowrap">`parallaxBackgroundImage`</span>. You can also set <span
class="nowrap">`parallaxBackgroundHorizontal`</span> and <span
class="nowrap">`parallaxBackgroundVertical`</span> the same way and must
also set <span class="nowrap">`parallaxBackgroundSize`</span> to have
your values take effect.

To set an image for a particular reveal.js slide, add <span
class="nowrap">`{data-background-image="/path/to/image"}`</span> to the
first slide-level heading on the slide (which may even be empty).

In reveal.js’s overview mode, the parallaxBackgroundImage will show up
only on the first slide.

Other reveal.js background settings also work on individual slides,
including <span class="nowrap">`data-background-size`</span>, <span
class="nowrap">`data-background-repeat`</span>, <span
class="nowrap">`data-background-color`</span>, <span
class="nowrap">`data-transition`</span>, and <span
class="nowrap">`data-transition-speed`</span>.

See the [reveal.js
documentation](https://github.com/hakimel/reveal.js#slide-backgrounds)
for more details.

For example in reveal.js:

    ---
    title: My Slideshow
    parallaxBackgroundImage: /path/to/my/background_image.png
    ---

    ## Slide One

    Slide 1 has background_image.png as its background.

    ## {data-background-image="/path/to/special_image.jpg"}

    Slide 2 has a special image for its background, even though the heading has no content.

Creating EPUBs with pandoc
==========================

EPUB Metadata
-------------

EPUB metadata may be specified using the [<span
class="nowrap">`--epub-metadata`</span>](#option--epub-metadata){.option}
option, but if the source document is Markdown, it is better to use a
[YAML metadata block](#extension-yaml_metadata_block). Here is an
example:

    ---
    title:
    - type: main
      text: My Book
    - type: subtitle
      text: An investigation of metadata
    creator:
    - role: author
      text: John Smith
    - role: editor
      text: Sarah Jones
    identifier:
    - scheme: DOI
      text: doi:10.234234.234/33
    publisher:  My Press
    rights: © 2007 John Smith, CC BY-NC
    ibooks:
      version: 1.3.4
    ...

The following fields are recognized:

<span class="nowrap">`identifier`</span>
:   Either a string value or an object with fields <span
    class="nowrap">`text`</span> and <span
    class="nowrap">`scheme`</span>. Valid values for <span
    class="nowrap">`scheme`</span> are <span
    class="nowrap">`ISBN-10`</span>, <span
    class="nowrap">`GTIN-13`</span>, <span class="nowrap">`UPC`</span>,
    <span class="nowrap">`ISMN-10`</span>, <span
    class="nowrap">`DOI`</span>, <span class="nowrap">`LCCN`</span>,
    <span class="nowrap">`GTIN-14`</span>, <span
    class="nowrap">`ISBN-13`</span>, <span
    class="nowrap">`Legal deposit number`</span>, <span
    class="nowrap">`URN`</span>, <span class="nowrap">`OCLC`</span>,
    <span class="nowrap">`ISMN-13`</span>, <span
    class="nowrap">`ISBN-A`</span>, <span class="nowrap">`JP`</span>,
    <span class="nowrap">`OLCC`</span>.

<span class="nowrap">`title`</span>
:   Either a string value, or an object with fields <span
    class="nowrap">`file-as`</span> and <span
    class="nowrap">`type`</span>, or a list of such objects. Valid
    values for <span class="nowrap">`type`</span> are <span
    class="nowrap">`main`</span>, <span
    class="nowrap">`subtitle`</span>, <span
    class="nowrap">`short`</span>, <span
    class="nowrap">`collection`</span>, <span
    class="nowrap">`edition`</span>, <span
    class="nowrap">`extended`</span>.

<span class="nowrap">`creator`</span>
:   Either a string value, or an object with fields <span
    class="nowrap">`role`</span>, <span class="nowrap">`file-as`</span>,
    and <span class="nowrap">`text`</span>, or a list of such objects.
    Valid values for <span class="nowrap">`role`</span> are [MARC
    relators](http://loc.gov/marc/relators/relaterm.html), but pandoc
    will attempt to translate the human-readable versions (like “author”
    and “editor”) to the appropriate marc relators.

<span class="nowrap">`contributor`</span>
:   Same format as <span class="nowrap">`creator`</span>.

<span class="nowrap">`date`</span>
:   A string value in <span class="nowrap">`YYYY-MM-DD`</span> format.
    (Only the year is necessary.) Pandoc will attempt to convert other
    common date formats.

<span class="nowrap">`lang`</span> (or legacy: <span class="nowrap">`language`</span>)
:   A string value in [BCP
    47](https://tools.ietf.org/html/bcp47) format. Pandoc will default
    to the local language if nothing is specified.

<span class="nowrap">`subject`</span>
:   A string value or a list of such values.

<span class="nowrap">`description`</span>
:   A string value.

<span class="nowrap">`type`</span>
:   A string value.

<span class="nowrap">`format`</span>
:   A string value.

<span class="nowrap">`relation`</span>
:   A string value.

<span class="nowrap">`coverage`</span>
:   A string value.

<span class="nowrap">`rights`</span>
:   A string value.

<span class="nowrap">`cover-image`</span>
:   A string value (path to cover image).

<span class="nowrap">`css`</span> (or legacy: <span class="nowrap">`stylesheet`</span>)
:   A string value (path to CSS stylesheet).

<span class="nowrap">`page-progression-direction`</span>
:   Either <span class="nowrap">`ltr`</span> or <span
    class="nowrap">`rtl`</span>. Specifies the <span
    class="nowrap">`page-progression-direction`</span> attribute for the
    [<span class="nowrap">`spine`</span>
    element](http://idpf.org/epub/301/spec/epub-publications.html#sec-spine-elem).

<span class="nowrap">`ibooks`</span>

:   iBooks-specific metadata, with the following fields:

    -   <span class="nowrap">`version`</span>: (string)
    -   <span class="nowrap">`specified-fonts`</span>: <span
        class="nowrap">`true`</span>|<span class="nowrap">`false`</span>
        (default <span class="nowrap">`false`</span>)
    -   <span class="nowrap">`ipad-orientation-lock`</span>: <span
        class="nowrap">`portrait-only`</span>|<span
        class="nowrap">`landscape-only`</span>
    -   <span class="nowrap">`iphone-orientation-lock`</span>: <span
        class="nowrap">`portrait-only`</span>|<span
        class="nowrap">`landscape-only`</span>
    -   <span class="nowrap">`binding`</span>: <span
        class="nowrap">`true`</span>|<span class="nowrap">`false`</span>
        (default <span class="nowrap">`true`</span>)
    -   <span class="nowrap">`scroll-axis`</span>: <span
        class="nowrap">`vertical`</span>|<span
        class="nowrap">`horizontal`</span>|<span
        class="nowrap">`default`</span>

The <span class="nowrap">`epub:type`</span> attribute
-----------------------------------------------------

For <span class="nowrap">`epub3`</span> output, you can mark up the
heading that corresponds to an EPUB chapter using the [<span
class="nowrap">`epub:type`</span>
attribute](http://www.idpf.org/epub/31/spec/epub-contentdocs.html#sec-epub-type-attribute).
For example, to set the attribute to the value <span
class="nowrap">`prologue`</span>, use this markdown:

    # My chapter {epub:type=prologue}

Which will result in:

    <body epub:type="frontmatter">
      <section epub:type="prologue">
        <h1>My chapter</h1>

Pandoc will output <span
class="nowrap">`<body epub:type="bodymatter">`</span>, unless you use
one of the following values, in which case either <span
class="nowrap">`frontmatter`</span> or <span
class="nowrap">`backmatter`</span> will be output.

  <span class="nowrap">`epub:type`</span> of first section   <span class="nowrap">`epub:type`</span> of body
  ---------------------------------------------------------- -------------------------------------------------
  prologue                                                   frontmatter
  abstract                                                   frontmatter
  acknowledgments                                            frontmatter
  copyright-page                                             frontmatter
  dedication                                                 frontmatter
  credits                                                    frontmatter
  keywords                                                   frontmatter
  imprint                                                    frontmatter
  contributors                                               frontmatter
  other-credits                                              frontmatter
  errata                                                     frontmatter
  revision-history                                           frontmatter
  titlepage                                                  frontmatter
  halftitlepage                                              frontmatter
  seriespage                                                 frontmatter
  foreword                                                   frontmatter
  preface                                                    frontmatter
  seriespage                                                 frontmatter
  titlepage                                                  frontmatter
  appendix                                                   backmatter
  colophon                                                   backmatter
  bibliography                                               backmatter
  index                                                      backmatter

Linked media
------------

By default, pandoc will download media referenced from any <span
class="nowrap">`<img>`</span>, <span class="nowrap">`<audio>`</span>,
<span class="nowrap">`<video>`</span> or <span
class="nowrap">`<source>`</span> element present in the generated EPUB,
and include it in the EPUB container, yielding a completely
self-contained EPUB. If you want to link to external media resources
instead, use raw HTML in your source and add <span
class="nowrap">`data-external="1"`</span> to the tag with the <span
class="nowrap">`src`</span> attribute. For example:

    <audio controls="1">
      <source src="http://example.com/music/toccata.mp3"
              data-external="1" type="audio/mpeg">
      </source>
    </audio>

Creating Jupyter notebooks with pandoc
======================================

When creating a [Jupyter
notebook](https://nbformat.readthedocs.io/en/latest/), pandoc will try
to infer the notebook structure. Code blocks with the class <span
class="nowrap">`code`</span> will be taken as code cells, and
intervening content will be taken as Markdown cells. Attachments will
automatically be created for images in Markdown cells. Metadata will be
taken from the <span class="nowrap">`jupyter`</span> metadata field. For
example:

    ---
    title: My notebook
    jupyter:
      nbformat: 4
      nbformat_minor: 5
      kernelspec:
         display_name: Python 2
         language: python
         name: python2
      language_info:
         codemirror_mode:
           name: ipython
           version: 2
         file_extension: ".py"
         mimetype: "text/x-python"
         name: "python"
         nbconvert_exporter: "python"
         pygments_lexer: "ipython2"
         version: "2.7.15"
    ---

    # Lorem ipsum

    **Lorem ipsum** dolor sit amet, consectetur adipiscing elit. Nunc luctus
    bibendum felis dictum sodales.

    ``` code
    print("hello")
    ```

    ## Pyout

    ``` code
    from IPython.display import HTML
    HTML("""
    <script>
    console.log("hello");
    </script>
    <b>HTML</b>
    """)
    ```

    ## Image

    This image ![image](myimage.png) will be
    included as a cell attachment.

If you want to add cell attributes, group cells differently, or add
output to code cells, then you need to include divs to indicate the
structure. You can use either [fenced divs](#extension-fenced_divs) or
[native divs](#extension-native_divs) for this. Here is an example:

    :::::: {.cell .markdown}
    # Lorem

    **Lorem ipsum** dolor sit amet, consectetur adipiscing elit. Nunc luctus
    bibendum felis dictum sodales.
    ::::::

    :::::: {.cell .code execution_count=1}
    ``` {.python}
    print("hello")
    ```

    ::: {.output .stream .stdout}
    ```
    hello
    ```
    :::
    ::::::

    :::::: {.cell .code execution_count=2}
    ``` {.python}
    from IPython.display import HTML
    HTML("""
    <script>
    console.log("hello");
    </script>
    <b>HTML</b>
    """)
    ```

    ::: {.output .execute_result execution_count=2}
    ```{=html}
    <script>
    console.log("hello");
    </script>
    <b>HTML</b>
    hello
    ```
    :::
    ::::::

If you include raw HTML or TeX in an output cell, use the \[raw
attribute\]\[Extension: <span
class="nowrap">`fenced_attribute`</span>\], as shown in the last cell of
the example above. Although pandoc can process “bare” raw HTML and TeX,
the result is often interspersed raw elements and normal textual
elements, and in an output cell pandoc expects a single, connected raw
block. To avoid using raw HTML or TeX except when marked explicitly
using raw attributes, we recommend specifying the extensions <span
class="nowrap">`-raw_html-raw_tex+raw_attribute`</span> when translating
between Markdown and ipynb notebooks.

Note that options and extensions that affect reading and writing of
Markdown will also affect Markdown cells in ipynb notebooks. For
example, [<span
class="nowrap">`--wrap=preserve`</span>](#option--wrap){.option} will
preserve soft line breaks in Markdown cells; [<span
class="nowrap">`--atx-headers`</span>](#option--atx-headers){.option}
will cause ATX-style headings to be used; and [<span
class="nowrap">`--preserve-tabs`</span>](#option--preserve-tabs){.option}
will prevent tabs from being turned to spaces.

Syntax highlighting
===================

Pandoc will automatically highlight syntax in [fenced code
blocks](#fenced-code-blocks) that are marked with a language name. The
Haskell library [skylighting](https://github.com/jgm/skylighting) is
used for highlighting. Currently highlighting is supported only for
HTML, EPUB, Docx, Ms, and LaTeX/PDF output. To see a list of language
names that pandoc will recognize, type <span
class="nowrap">`pandoc --list-highlight-languages`</span>.

The color scheme can be selected using the [<span
class="nowrap">`--highlight-style`</span>](#option--highlight-style){.option}
option. The default color scheme is <span
class="nowrap">`pygments`</span>, which imitates the default color
scheme used by the Python library pygments (though pygments is not
actually used to do the highlighting). To see a list of highlight
styles, type <span
class="nowrap">`pandoc --list-highlight-styles`</span>.

If you are not satisfied with the predefined styles, you can use [<span
class="nowrap">`--print-highlight-style`</span>](#option--print-highlight-style){.option}
to generate a JSON <span class="nowrap">`.theme`</span> file which can
be modified and used as the argument to [<span
class="nowrap">`--highlight-style`</span>](#option--highlight-style){.option}.
To get a JSON version of the <span class="nowrap">`pygments`</span>
style, for example:

    pandoc --print-highlight-style pygments > my.theme

Then edit <span class="nowrap">`my.theme`</span> and use it like this:

    pandoc --highlight-style my.theme

If you are not satisfied with the built-in highlighting, or you want
highlight a language that isn’t supported, you can use the [<span
class="nowrap">`--syntax-definition`</span>](#option--syntax-definition){.option}
option to load a [KDE-style XML syntax definition
file](https://docs.kde.org/stable5/en/applications/katepart/highlight.html).
Before writing your own, have a look at KDE’s [repository of syntax
definitions](https://github.com/KDE/syntax-highlighting/tree/master/data/syntax).

To disable highlighting, use the [<span
class="nowrap">`--no-highlight`</span>](#option--no-highlight){.option}
option.

Custom Styles
=============

Custom styles can be used in the docx and ICML formats.

Output
------

By default, pandoc’s docx and ICML output applies a predefined set of
styles for blocks such as paragraphs and block quotes, and uses largely
default formatting (italics, bold) for inlines. This will work for most
purposes, especially alongside a <span
class="nowrap">`reference.docx`</span> file. However, if you need to
apply your own styles to blocks, or match a preexisting set of styles,
pandoc allows you to define custom styles for blocks and text using
<span class="nowrap">`div`</span>s and <span
class="nowrap">`span`</span>s, respectively.

If you define a <span class="nowrap">`div`</span> or <span
class="nowrap">`span`</span> with the attribute <span
class="nowrap">`custom-style`</span>, pandoc will apply your specified
style to the contained elements. So, for example using the <span
class="nowrap">`bracketed_spans`</span> syntax,

    [Get out]{custom-style="Emphatically"}, he said.

would produce a docx file with “Get out” styled with character style
<span class="nowrap">`Emphatically`</span>. Similarly, using the <span
class="nowrap">`fenced_divs`</span> syntax,

    Dickinson starts the poem simply:

    ::: {custom-style="Poetry"}
    | A Bird came down the Walk---
    | He did not know I saw---
    :::

would style the two contained lines with the <span
class="nowrap">`Poetry`</span> paragraph style.

For docx output, styles will be defined in the output file as inheriting
from normal text, if the styles are not yet in your reference.docx. If
they are already defined, pandoc will not alter the definition.

This feature allows for greatest customization in conjunction with
[pandoc filters](http://pandoc.org/filters.html). If you want all
paragraphs after block quotes to be indented, you can write a filter to
apply the styles necessary. If you want all italics to be transformed to
the <span class="nowrap">`Emphasis`</span> character style (perhaps to
change their color), you can write a filter which will transform all
italicized inlines to inlines within an <span
class="nowrap">`Emphasis`</span> custom-style <span
class="nowrap">`span`</span>.

For docx output, you don’t need to enable any extensions for custom
styles to work.

Input
-----

The docx reader, by default, only reads those styles that it can convert
into pandoc elements, either by direct conversion or interpreting the
derivation of the input document’s styles.

By enabling the [<span class="nowrap">`styles`</span>
extension](#ext-styles) in the docx reader ([<span
class="nowrap">`-f docx+styles`</span>](#option--from){.option}), you
can produce output that maintains the styles of the input document,
using the <span class="nowrap">`custom-style`</span> class. Paragraph
styles are interpreted as divs, while character styles are interpreted
as spans.

For example, using the <span
class="nowrap">`custom-style-reference.docx`</span> file in the test
directory, we have the following different outputs:

Without the <span class="nowrap">`+styles`</span> extension:

    $ pandoc test/docx/custom-style-reference.docx -f docx -t markdown
    This is some text.

    This is text with an *emphasized* text style. And this is text with a
    **strengthened** text style.

    > Here is a styled paragraph that inherits from Block Text.

And with the extension:

    $ pandoc test/docx/custom-style-reference.docx -f docx+styles -t markdown

    ::: {custom-style="FirstParagraph"}
    This is some text.
    :::

    ::: {custom-style="BodyText"}
    This is text with an [emphasized]{custom-style="Emphatic"} text style.
    And this is text with a [strengthened]{custom-style="Strengthened"}
    text style.
    :::

    ::: {custom-style="MyBlockStyle"}
    > Here is a styled paragraph that inherits from Block Text.
    :::

With these custom styles, you can use your input document as a
reference-doc while creating docx output (see below), and maintain the
same styles in your input and output files.

Custom writers
==============

Pandoc can be extended with custom writers written in
[lua](http://www.lua.org). (Pandoc includes a lua interpreter, so lua
need not be installed separately.)

To use a custom writer, simply specify the path to the lua script in
place of the output format. For example:

    pandoc -t data/sample.lua

Creating a custom writer requires writing a lua function for each
possible element in a pandoc document. To get a documented example which
you can modify according to your needs, do

    pandoc --print-default-data-file sample.lua

A note on security
==================

If you use pandoc to convert user-contributed content in a web
application, here are some things to keep in mind:

1.  Although pandoc itself will not create or modify any files other
    than those you explicitly ask it create (with the exception of
    temporary files used in producing PDFs), a filter or custom writer
    could in principle do anything on your file system. Please audit
    filters and custom writers very carefully before using them.

2.  If your application uses pandoc as a Haskell library (rather than
    shelling out to the executable), it is possible to use it in a mode
    that fully isolates pandoc from your file system, by running the
    pandoc operations in the <span
    class="nowrap">`PandocPure`</span> monad. See the document [Using
    the pandoc API](http://pandoc.org/using-the-pandoc-api.html) for
    more details.

3.  Pandoc’s parsers can exhibit pathological performance on some
    corner cases. It is wise to put any pandoc operations under a
    timeout, to avoid DOS attacks that exploit these issues. If you are
    using the pandoc executable, you can add the command line options
    <span class="nowrap">`+RTS -M512M -RTS`</span> (for example) to
    limit the heap size to 512MB.

4.  The HTML generated by pandoc is not guaranteed to be safe. If <span
    class="nowrap">`raw_html`</span> is enabled for the Markdown input,
    users can inject arbitrary HTML. Even if <span
    class="nowrap">`raw_html`</span> is disabled, users can include
    dangerous content in attributes for headings, spans, and
    code blocks. To be safe, you should run all the generated HTML
    through an HTML sanitizer.

Authors
=======

Copyright 2006–2019 John MacFarlane (jgm@berkeley.edu). Released under
the
[GPL](http://www.gnu.org/copyleft/gpl.html "GNU General Public License"),
version 2 or greater. This software carries no warranty of any kind.
(See COPYRIGHT for full copyright and warranty notices.) For a full list
of contributors, see the file AUTHORS.md in the pandoc source code.

<div class="section footnotes" role="doc-endnotes">

------------------------------------------------------------------------

1.  <div id="fn1">

    </div>

    The point of this rule is to ensure that normal paragraphs starting
    with people’s initials, like

        B. Russell was an English philosopher.

    do not get treated as list items.

    This rule will not prevent

        (C) 2007 Joe Smith

    from being interpreted as a list item. In this case, a backslash
    escape can be used:

        (C\) 2007 Joe Smith

    [↩︎](#fnref1){.footnote-back}

2.  <div id="fn2">

    </div>

    I have been influenced by the suggestions of [David
    Wheeler](http://www.justatheory.com/computers/markup/modest-markdown-proposal.html).[↩︎](#fnref2){.footnote-back}

3.  <div id="fn3">

    </div>

    This scheme is due to Michel Fortin, who proposed it on the
    [Markdown discussion
    list](http://six.pairlist.net/pipermail/markdown-discuss/2005-March/001097.html).[↩︎](#fnref3){.footnote-back}

4.  <div id="fn4">

    </div>

    To see why laziness is incompatible with relaxing the requirement of
    a blank line between items, consider the following example:

        bar
        :    definition
        foo
        :    definition

    Is this a single list item with two definitions of “bar,” the first
    of which is lazily wrapped, or two list items? To remove the
    ambiguity we must either disallow lazy wrapping or require a blank
    line between list items.[↩︎](#fnref4){.footnote-back}

</div>

</div>

</div>

</div>
