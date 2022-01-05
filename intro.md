---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Demonstration of the alignment issue

## Just regular image insert

Here {numref}`fig-jupyterbook-left` left aligned, then  {numref}`fig-jupyterbook-center` center aligned and {numref}`fig-jupyterbook-right` right aligned.

This chapter demonstrates that regular figure insertions work just fine.

```{figure} figs/jupyterbook.png
---
width: 30%
name: fig-jupyterbook-left
align: left
---
Jypyterbook logo left aligned
```

```{figure} figs/jupyterbook.png
---
width: 30%
name: fig-jupyterbook-center
align: center
---
Jypyterbook logo center aligned
```

```{figure} figs/jupyterbook.png
---
width: 30%
name: fig-jupyterbook-right
align: right
---
Jypyterbook logo right aligned
```

## Pandas dataframe glued

Here {numref}`tbl-pandas-left` left aligned, then  {numref}`tbl-pandas-center` center aligned and {numref}`tbl-pandas-right` right aligned with random text in between.

This chapter demonstrates that captions adhere to alignment commands but glued pandas dataframes do not.

```{code-cell} ipython3
:tags: ["remove-cell"]
from myst_nb import glue
import pandas as pd
import numpy as np

pow = ["A", "B", "C"]
tol = ["+-2 dB", "+-3 dB", "+-4 dB",]
col_n = ["Class","F2", "F3"]
row_n = ["Class I", "Class II", "Class III",]

data = np.array([row_n, pow, tol]).transpose()

df= pd.DataFrame(data, columns=col_n).set_index("Class")
glue("glued_df", df) 
```

Random text1

```{glue:figure} glued_df
:name: "tbl-pandas-left"
:align: left

Pandas table left aligned
```

Random text2

```{glue:figure} glued_df
:name: "tbl-pandas-center"
:align: center

Pandas table center aligned
```

Random text3

```{glue:figure} glued_df
:name: "tbl-pandas-right"
:align: right

Pandas table right aligned
```

## Pandas dataframe glued without texts in between

Here {numref}`tbl-pandas-left-again` left aligned, then  {numref}`tbl-pandas-center-again` center aligned and {numref}`tbl-pandas-right-again` right aligned.

In addition to the previous chapter this chapter should demonstrate the completely missing table of {numref}`tbl-pandas-center-again` (version dependent). The caption exists but the figure (rendered dataframe) is missing.

```{glue:figure} glued_df
:name: "tbl-pandas-left-again"
:align: left

Pandas table left aligned
```

```{glue:figure} glued_df
:name: "tbl-pandas-center-again"
:align: center

Pandas table center aligned
```

```{glue:figure} glued_df
:name: "tbl-pandas-right-again"
:align: right

Pandas table right aligned
```
