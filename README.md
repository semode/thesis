# cam-thesis

    a LaTeX thesis template for Cambridge PhD students

Want to write a thesis? Well, all you need is this template, one of the existing samples&mdash;which can be found in the [`./Samples/`](https://github.com/cambridge/thesis/tree/master/Samples) folder&mdash;, and some content.

The samples are typically neatly structured, have their own special cosmetic features, and are based on theses of other PhD students.

## Quicker start

Copy all files from this directory (where you found this `README` file) to your
desired location.

Now you can start writing your thesis using the `thesis.tex` file.

## How will it look like?

Your thesis document will look something like this (using the Adobe Sabon font and the _clean_ sample, which can be found in [`./Samples/clean`](https://github.com/cambridge/thesis/tree/master/Samples/clean)):

* [Thesis Sample (PDF)](https://github.com/downloads/cambridge/thesis/thesis.pdf)

The template also supports DVI and PS formats. All three formats are generated
by the provided `Makefile`.

## Producing PDF, DVI and PS documents

### Build your thesis

To build your thesis, run:

    make

This should build `thesis.dvi`, `thesis.ps` and `thesis.pdf` documents.

### Clean unwanted files

To clean unwanted clutter (all LaTeX auto-generated files), run:

    make clean

To clean absolutely all files produced by `make`, run:

    make distclean

For other build options, refer to the `Makefile` file itself.

-------------------------------------------------------------------------------

# Usage details

## Class options

`cam-thesis` supports all the options of the standard `report` class (on which
it is based).

It also supports some custom options.

*   `techreport`: formats the document as a technical report. Here is a list of
    formatting points in which the technical report differs from a normal thesis
    (see [guidelines](http://www.cl.cam.ac.uk/techreports/submission.html) for
    more information):

    *   different margins (left and right margins are 25mm, top and bottom
        margins are 20mm),
    *   normal line spacing (instead of one-half spacing),
    *   no custom title page,
    *   no declaration,
    *   page count starts with 3,
    *   if the `hyperref` package is used, the option `pdfpagelabels=false` will
        be passed to it.

*   `notimes`: tells the class not to use the _times_ font. This option is
    implied by the `nopackages`.

*   `nopackages`: tells the class not to use any non-essential packages (this
    option implies the `notimes` option).

    _Note_: If this option is not specified, then the class will use the
    following non-essential packages:

    * `times` (can also be excluded by using the `notimes` option),
    * `amsmath`
    * `amssymb`
    * `amsthm`

-------------------------------------------------------------------------------

# Troubleshooting

## _Q1_: I found a bug in the template. Where do I report bugs?

You can report issues through
[our GitHub repository](https://github.com/cambridge/thesis/issues).

You can also mail
[the maintainers](https://github.com/cambridge/thesis/contributors) directly.

## _Q2_: Where can I find the thesis formatting guidelines this class is based on?

The University of Cambridge guidelines:

> [http://www.admin.cam.ac.uk/students/studentregistry/exams/submission/phd/format.html](http://www.admin.cam.ac.uk/students/studentregistry/exams/submission/phd/format.html)

The Computer Laboratory guidelines:

> [http://www.cl.cam.ac.uk/local/phd/typography/](http://www.cl.cam.ac.uk/local/phd/typography/)     

The Computer Laboratory guidelines for technical reports:

> [http://www.cl.cam.ac.uk/techreports/submission.html](http://www.cl.cam.ac.uk/techreports/submission.html)

## _Q3_: Can I use my own Makefile?

By all means. Here is a very nice (and smart) `Makefile` built specifically for
LaTeX:

> [http://code.google.com/p/latex-makefile/](http://code.google.com/p/latex-makefile/)

## _Q4_: But what if I don't want the template files in my thesis directory?

Put the files and folders listed below into a directory where LaTeX can find them (for more
info see __[1]__):

    cam-thesis.cls
    CUni.eps
    CUni.pdf
    CollegeShields/


> __[1]__ You can put these files either into the standard LaTeX directory for
> classes __[2]__, or a directory listed in your `TEXINPUTS` environment variable.
>
> __[2]__ The location of the standard LaTeX class directory depends on which LaTeX
> installation and operating system you use. For example, for TeX Live on Fedora
> 14 it is `/usr/share/texmf/tex/latex/base`.
>
> In any case, after this, LaTeX will still not be able find your class. You
> will have to rebuild the package index. This procedure also depends on your
> installation specifics, but for TeX Live you have to run the `texhash` command.
>
> For more comprehensive information refer to
> [LaTeX Wikibooks](http://en.wikibooks.org/wiki/LaTeX/Packages/Installing_Extra_Packages).

## _Q5_: Where can I find newer versions of the University of Cambridge logo?

The university updates its logo every now and then. You can find up-to-date
logos on [this page](http://www.admin.cam.ac.uk/offices/communications/services/logos/)
(subject to change without notice).

Download and exchange the new logos with `CUni.eps` and/or `CUni.pdf`.

## _Q6_: My college's shield/coat of arms/crest is not included. Why u no include it?

The shields are being added on the go (when somebody, who uses them, provides them).

If you find a distributable vector-based image of your college's shield you can report it as an issue or mail it to contributors directly (refer to question __Q1__ above).

## _Q7_: Where can I find extra fonts (like Adobe Sabon, Adobe Utopia etc.)?

The Computer Laboratory provides some [here](http://www.cl.cam.ac.uk/local/sys/unix/applications/tex/#clfonts).

After you've installed the fonts, add somewhere in the preamble (before `\begin{document}`) the following command:

    \renewcommand\rmdefault{psb}

## _Q8_: How should I count the number of words in my thesis?

There is [a page](http://www.cl.cam.ac.uk/local/phd/writingup.html) on the Computer Lab's web site. They recommend using this command:

    ps2ascii thesis.pdf | wc -w

--------------------------------------------------------------------------------

# TODO list

*   Fill PDF's meta tags (e.g.: author, title, keywords etc.).
*   It is debatable which packages are non-essential. We could reclassify this.
