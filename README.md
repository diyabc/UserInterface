# Graphical User Interface for DIYABC-RF software

We provide a graphical user interface (GUI) for the DIYABC-RF software [1], 
called DIYABC-RF GUI.

Please check the project [website](https://diyabc.github.io/) for 
additional information and detailed documentation.

DIYABC-RF GUI is available as a standalone application, or in a R package called `diyabcGUI` as a `shiny` web app. You can either install the standalone app, or the `diyabcGUI` package and run the DIYABC-RF GUI as a standard `shiny` app, c.f. [below](#r-package-installation).

## Installation

### Standalone app

For Windows and MacOS users, please download the latest release at 
<https://github.com/diyabc/diyabcGUI/releases/latest>.

For the moment, the standalone app is not available for Linux users. 
Nonetheless, Linux users can install the `diyabcGUI` package, c.f. 
[below](#r-package-installation), and 
run the DIYABC-RF GUI as a standard `shiny` app.

> **Note:** if encountering instability in the standalone app, we recommend to install and use the `shiny` app available in the `diyabcGUI` R package, c.f. [below](#r-package-installation).


### R package installation

1. Install `devtools` package if not available
```R
install.packages("devtools")
```

2. Install `diyabcGUI` package
```R
devtools::install_github(
    "diyabc/diyabcGUI",
    subdir = "R-pkg"
)
```

3. Launch the interface
```R
library(diyabcGUI)
diyabc()
```

The function `diyabc()` will launch DIYABC-RF GUI as a standard `shiny` web app, that you will be able to use either in your web browser or in the Rstudio `shiny` app viewer.

To run simultaneously mutliple instance of DIYABC-RF GUI, e.g. to simultaneously manage and run multiple projects, you just need to run several times the function `diyabc()` from R (this is not possible from RStudio).

### Shiny server installation

As a `shiny` app, DIYABC-RF GUI can be installed and run from a Shiny server. To do so, you just need (on Unix system, please adapt for Windows server) to:

1. install the `diyabcGUI` package on your system, c.f. [above](#r-package-installation)
2. manage the file access rights so that the Shiny server has access to the R package installation directory
3. Create a symbolic link to the directory given by the R command `system.file("application", package = "diyabcGUI")` inside the `site_dir` folder configured in `/etc/shiny-server/shiny-server.conf` (by default `/srv/shiny-server`), e.g.:
```bash
ln -s /path/to/R_LIBS/diyabcGUI/application /srv/shiny-server/diyabc
```
4. DIYABC-RF GUI is now available on your server at `https://my.shiny.server.address/diyabc`

## Reference

[1] Collin F-D, Raynal L, Durif G, Gautier M, Vitalis R, Lombaert E., Marin J-M, Estoup A (2020) DIYABC Random Forest v1.0: extending approximate Bayesian computation with supervised machine learning to infer demographic history from genetic polymorphisms. Submitted to Molecular Ecology Resources.