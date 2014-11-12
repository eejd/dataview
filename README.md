Synesthesia for R
========
A terminal tool for overviewing your workspace and objects in a clean, colorful and human readable way.

If you prefer to do your R work in the terminal (probably in combination with Vim or Emacs)
`synesthesia` is a great little tool for keeping track of cluttered workspaces and disecting obscure objects.
It centers around the functions `whos` inspired by the same function in MATLAB,
`entry.view` inspired by data base systems,
and `heat.view` that can visualize long vectors in a very compact manner (especially factors).

Installation
------------
As it is a complete reimplementation of the `dataview` package, the installation procedure is a bit dirty at the moment.
It will soon take over as the official release and be published on CRAN, and `dataview` will be discontinued. 
```
library(devtools)
install_github("backlin/xtermStyle")
install_github("backlin/dataview@develop")
```
Then you typically also want to add these lines to the end of your `~/.Rprofile` to auto-load the package and hide all objects created during the startup
```
require(synesthesia)
whos.exclude(ls())
```
and perhaps also
```
print.factor <- heat.view
```

Usage & Functionality
---------------------
This is what it does:

![Synesthesia demo](https://raw.githubusercontent.com/backlin/dataview/images/images/synesthesia.png)

If you find yourself calling `whos` often, you probably want to check out the `browse` function too.

Colors
------
The color schemes used by Synesthesia is defined in the `xtermStyle` package. To change the default palette (dark on light terminal background) you must attach it and do the following:
```
require(xtermStyle)
style.palette("light") # Designed for dark terminal background
```
`style.palette` also let's you define your own palette if you are not happy with the pre-defined ones.