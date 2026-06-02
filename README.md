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
| 2nd Article/Manuscript Template | [https://github.com/svmiller/quarto-templates/tree/main/qarticle2](`qarticle2`) | `quarto use template svmiller/quarto-templates/qarticle2` |
| 3rd Article/Manuscript Template | [https://github.com/svmiller/quarto-templates/tree/main/qarticle3](`qarticle3`) | `quarto use template svmiller/quarto-templates/qarticle3` |

You could alternatively do something like `quarto add svmiller/quarto-templates/qarticle3`, 
but that would download just the contents of the `_extensions` directory. My 
templates tend to have a lot of moving pieces and seeing them in the `.qmd`
file can help the user make sense of them.