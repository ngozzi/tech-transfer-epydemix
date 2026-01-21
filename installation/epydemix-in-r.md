
# Using **epydemix** in an R session

This guide assumes you have R and RStudio installed. If not, see [r-setup.md](r-setup.md) first.

The R package [**reticulate**](https://rstudio.github.io/reticulate) offers an
easy way to use the **epydemix** package in R, since it allows to import Python
modules within an R session, automatically handling the conversion between
Python and R data types.

## Installing the **reticulate** package

To install the **reticulate** package from CRAN use the following statement:

```r
install.packages("reticulate")
```

## Importing the **epydemix** package in R

Once **reticulate** is installed, one can load this package with
`library(reticulate)`, and then import **epydemix**. The recommended way is by
calling `py_require()`, which allows to declare Python requirements for an R
session, followed by the `import()` statement.

**Reticulate** will automatically create and use an ephemeral Python
environment that satisfies the requirements, downloading and installing the
**epydemix** package and its dependencies if not already installed.

Essentially, one needs to do the following:

```r
library(reticulate)
py_require("epydemix")
epydemix <- import("epydemix")
```

It is then possible to call functions and access other objects defined in
**epydemix** by using the `$` operator:

```r
library(reticulate)
py_require("epydemix")
epydemix <- import("epydemix")

# A simple SIR model
sir_model <- epydemix$EpiModel(
    name="SIR Model", 
    compartments=list("S", "I", "R")
)

sir_model$add_transition("S", "I", "mediated", list(0.3, "I"))
sir_model$add_transition("I", "R", "spontaneous", 0.1)
```

### Keyword arguments

Keyword arguments can be passed to functions by applying the splice operator
`!!!` on _named_ lists, which are the R equivalent of Python dictionaries. This
also allows to specify the arguments in any desired order:

```r
[...]
sir_model$add_transition(!!!list(
    kind="mediated", 
    source="S", 
    target="I", 
    params=list(0.3, "I"))
)
sir_model$add_transition(!!!list(
    kind="spontaneous", 
    source="I", 
    target="R", 
    params=0.1)
)
```

## Further reading

For more details about how to install Python packages and declaring
requirements, please refer to [Installing Python
Packages](https://rstudio.github.io/reticulate/articles/python_packages.html).

Also particularly useful is [Calling Python from
R](https://rstudio.github.io/reticulate/articles/calling_python.html), which
describes, among other things, how to deal with different data types in R
and Python.
