# Build Documentation
```bash
# Build all or
jupyter-book build --all .
```

# This repository demonstrates the glued pandas dataframe alignment issue.

## Demonstration that regular image inserts align properly

![image](./figs/regular-image.png)

## Demonstration that glued pandas dataframes do not align

![image](./figs/pandas-df-glued1.png)

## Demonstration that in addition with certain OS - installed package combinations dataframes do not render at all.

This is deterministic behavior of this use case on macOS Catalina 10.15.7, Python 3.9.9 (Homebrew installed), jupyterbook 0.12.1, myst-nb 0.13.1, Pandas 1.3.5.
Install requirements for jupyterbook and pandas are listed in requirements.txt.

Same issue is not present on Ubuntu 20.04, Python 3.8.10, jupyterbook 1.12.0, myst-nb 0.13.1, pandas 1.3.4

![image](./figs/pandas-df-glued2.png)
