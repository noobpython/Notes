# Notes
This is a repository of my notes

#### Here is how you install jupyter nbextensions
```
pip install jupyter_nbextensions_configurator

jupyter nbextensions_configurator enable --user

pip install jupyter contrib_nbextensions

pip install autopep8

pip install npm

pip install nodejs

jupyter contrib nbextension install --user

```

Read below for more useful tools for data-science
https://towardsdatascience.com/bringing-the-best-out-of-jupyter-notebooks-for-data-science-f0871519ca29


```
pip install qgrid
jupyter nbextension enable --py --sys-prefix qgrid
```


#### 6. Embedding URLs, PDFs, and Youtube Videos
```
#Note that http urls will not be displayed. Only https are allowed inside the Iframe
from IPython.display import IFrame
IFrame('https://en.wikipedia.org/wiki/HTTPS', width=800, height=450)
```
![Embedding URLs](https://miro.medium.com/max/658/1*hKNCLc-0g8HubqRZWdWr5Q.gif)

```
from IPython.display import IFrame
IFrame('https://arxiv.org/pdf/1406.2661.pdf', width=800, height=450)
```
![Embedding PDFs](https://miro.medium.com/max/641/1*Trjh8qyP9i0o4Z1LJYp8mg.png)

