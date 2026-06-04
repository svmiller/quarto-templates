# Steve's Quarto Templates

This is my repository for Quarto templates. Installing Quarto templates, as I
understand it, works a bit different than my familiar approach with R Markdown
templates. In the latter case, a single copy can live in an R package the user
would install. In Quarto, you have to do something different that amounts to
different copies of the template by particular project. That at least has 
value for co-authored projects, though.

# What's Included

| **Template** | **Directory** | **Installation** | 
|:------------:|:-------------:|:-----------------|
| 2nd Article/Manuscript Template | [`qarticle2`](https://github.com/svmiller/quarto-templates/tree/main/qarticle2) | `quarto use template svmiller/quarto-templates/qarticle2` |
| 3rd Article/Manuscript Template | [`qarticle3`](https://github.com/svmiller/quarto-templates/tree/main/qarticle3) | `quarto use template svmiller/quarto-templates/qarticle3` |

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
| `title-subtitle:` | Defaults to FALSE. If TRUE, a subtitle is displayed on same line as title. If FALSE, an optional subtitle (if supplied) is on the line below the title |
| `acmsans:`    | Defaults to FALSE. If TRUE, invokes use of a sans serif font to mimic [ACM template](https://quarto-journals.github.io/acm/).[^recommend] |

[^recommend]: If you use this, I recommend you keep `fontsize:` at 11 and specify "Libertinus Sans" or "Linux Biolinum O" in the `sansfont:` argument.