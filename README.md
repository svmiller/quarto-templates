# Steve's Quarto Templates

This is my repository for Quarto templates. Installing Quarto templates, as I
understand it, works a bit different than my familiar approach with R Markdown
templates. In the latter case, a single copy can live in an R package the user
would install. In Quarto, you have to do something different that amounts to
different copies of the template by particular project. That at least has 
value for co-authored projects, though.

Quarto is popular among researchers in part because it's not limited to the R
programming language, like R Markdown is. Be advised the basic formatting of
my templates does not lean on the use of the R programming language, though my 
templates often come with R examples in the document. You can scrub the R code
and use the programming language of your choice.

You can see some example documents in [the `examples` directory in this Github repository](https://github.com/svmiller/quarto-templates/tree/main/examples).

# What's Included

| **Template** | **Directory** | **Installation** | 
|:------------:|:-------------:|:-----------------|
| 2nd Article/Manuscript Template | [`qarticle2`](https://github.com/svmiller/quarto-templates/tree/main/qarticle2) | `quarto use template svmiller/quarto-templates/qarticle2` |
| 3rd Article/Manuscript Template | [`qarticle3`](https://github.com/svmiller/quarto-templates/tree/main/qarticle3) | `quarto use template svmiller/quarto-templates/qarticle3` |
| 2nd Syllabus Template | [`qsyllabus2`](https://github.com/svmiller/quarto-templates/tree/main/qsyllabus2) | `quarto use template svmiller/quarto-templates/qsyllabus2` |
| Stockholm University EKOHIST Thesis Template | [`qekohist-thesis`](https://github.com/svmiller/quarto-templates/tree/main/qekohist-thesis) | `quarto use template svmiller/quarto-templates/qekohist-thesis` |

You could alternatively do something like `quarto add svmiller/quarto-templates/qarticle3`, 
but that would download just the contents of the `_extensions` directory. My 
templates tend to have a lot of moving pieces and seeing them in the `.qmd`
file can help the user make sense of them.

# Article 2's Important YAML Parameters

In addition to the standard fare in document YAML and other things unique to
Quarto, the following YAML arguments are unique to my templates and/or this
particular template.

| **Argument** | **Description** |
|:------------:|:----------------|
| `anonymous:` | Defaults to FALSE. If TRUE, suppresses identifying author information for presentation. Also moves tables and figures to back of the document. |
| `removetitleabstract:` | Default to FALSE. If TRUE, removes title and abstract. Some journals want this for peer review. Will also anonymize document presentation, if not document information on the PDF side of things. |
| `title-subtitle:` | Defaults to FALSE. If TRUE, a subtitle is displayed on same line as title. If FALSE, an optional subtitle (if supplied) is on the line below the title |
| `acmsans:`    | Defaults to FALSE. If TRUE, invokes use of a sans serif font to mimic [ACM template](https://quarto-journals.github.io/acm/).[^recommend] |
| `paper-info:` | Optional stuff to include for your paper (e.g. funding information? DOI? JEL codes?). See YAML of example document for how to use. |
| `endnotes:`   | Defaults to FALSE. If TRUE, footnotes become endnotes. I hate it too, but some journals want that for peer review. |
| `pandocparas:` | Defaults to FALSE. If TRUE, default paragraph style by Pandoc is used (i.e. no paragraph indents, spaces between paragraphs). If FALSE, default LaTeX paragraphs are used (i.e. no indent on first paragraph in a section, small indent on ensuing paragraphs) |
| `endfloat:` | Defaults to FALSE. If TRUE, figure and table replacement moved to back with "[Figure/Table N] about here" placeholder text in the document using the LaTeX `endfloat` package. Observed *only* when `anonymous: TRUE`. |

[^recommend]: If you use this, I recommend you keep `fontsize:` at 11 and specify "Libertinus Sans" or "Linux Biolinum O" in the `sansfont:` argument.

# Article 3's Important YAML Parameters

In addition to the standard fare in document YAML and other things unique to
Quarto, the following YAML arguments are unique to my templates and/or this
particular template. Many of [the formatting quirks I built into my second
article/manuscript template](https://svmiller.com/blog/2020/09/another-rmarkdown-article-template/)
also appear in [the one I created in 2023](https://svmiller.com/blog/2023/05/a-third-rmarkdown-article-manuscript-template/) 
and extend here for Quarto.

## `solo-author`, `two-authors`, and `n-authors`

Behavior in this template changes contingent on the number of authors. However,
this needs to be declared by the user as in an argument in the YAML. If there
are two authors, declare `two-authors: TRUE` in the YAML. If there are more than
two authors, declare `n-authors: TRUE` in the YAML. The default formatting assumes
there is just one author. You don't need to declare `solo-author: TRUE` in the
YAML for just one author as this is the fallback in the absence of 
`two-authors: TRUE` or `n-authors: TRUE`.

## `alternate-layout`

Defaults to `FALSE`, but when set to `TRUE`, this adjusts where the author and
contact info should be. When `FALSE`, the author(s) affiliation information and
contact information is placed adjacent to the abstract and above (optional)
paper information. When `TRUE`, the author(s) affiliation information is
underneath the listing of the authors while the contact information (i.e. emails)
remain adjacent to the abstract. I recommend setting `alternate-layout: TRUE` for
manuscripts when `n-authors: TRUE`. Adjust to your heart's content.

## `remove-emails`

Defaults to `FALSE`. If `TRUE`, author emails are scrubbed from the document.
This is perhaps useful for multi-author documents and/or when a corresponding
email in the acknowledgement underneath the title is sufficient.

# Syllabus 2's Important YAML Parameters

This is a fairly straightforward template, but two YAML parameters are unique
in this template.

## `two-teachers`, and `n-teachers`

Behavior in this template changes contingent on the number of teachers in
the course. However, this needs to be declared by the user as in an argument in 
the YAML. If there are two teachers, declare `two-authors: TRUE` in the YAML. If 
there are more than two teachers, declare `n-teachers: TRUE` in the YAML. The 
default formatting assumes there is just one teacher.

Some other arguments:

| **Argument** | **Description** |
|:------------:|:----------------|
| `title` | Title of the class |
| `author` | Name(s) of the professor(s) |
| `term` | The term of the class (e.g. Fall 2024, Spring 2025, Summer 2025) |
| `dates` | A basic date range for the course (e.g. Feb. 20 - March 21) |
| `fontawesome` | Logical, defaults to TRUE, for use of Font Awesome icons |
| `email` | The email for the "course responsible" professor. It's a thing here. |
| `web` | Class website. Technically optional, but you really should use it. |
| `office` | Your office location. Technically optional, but you really should use it. |

# EKOHIST Thesis's Important YAML Parameters

This is a boutique template of potential use for MA students in the Department
of Economic History and International Relations, where I currently work. I advise
students to not change much in the YAML for the `.qmd` file. There is no option
to anonymize the document. It wouldn't make sense in this context. If the student
does not have figures and/or tables---as odd as that seems for a thesis---you can
change `lof` and/or `lot` to be `FALSE`. Both arguments control whether a list
of figures and a list of tables, respectively, are generated in the document
after the table of contents.


