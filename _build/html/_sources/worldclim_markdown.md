---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Worldclim with MyST Markdown

```{code-cell} ipython3
:tags: ["remove-input"]
import pandas as pd
import cartopy.crs as ccrs
import hvplot.xarray
import hvplot.pandas
import xarray as xr
from bokeh.plotting import figure, show, output_notebook
```

## Plot should go here 3

```{code-cell} ipython3
:tags: ["full-width"]
ds = xr.open_dataarray('worldclim_data/wc2.1_10m_elev.tif')
ds = ds.sel(band=1)
ds.drop(['band','spatial_ref']).hvplot(x='x',y='y',width=1500,height=1000,cmap='plasma',xlabel='lon')
```