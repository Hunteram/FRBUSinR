# FRBUSinR
README.md
========================================================
Study of FRB/US model packages from the Federal Reserve (and perhaps port to R language)
--------------------------------------------------------

### About:

[FRB/US model packages](https://www.federalreserve.gov/econresdata/frbus/us-models-package.htm):

"The main FRB/US model package is a self-contained set of equations, data, programs and documentation that enables various types of simulations and provides information about the model's structure."

"NOTE: The programs for simulating the FRB/US model are written for use with the software EViews, available at [www.EViews.com](http://www.EViews.com)"

Github: [proudindiv/FRBUSinR](https://github.com/proudindiv/FRBUSinR):

Unfortunately, EViews is propritary software and hence not readily accessible.  My thought is to explore the information provided by the Federal Reserve using the open source R-language and other freely available tools for truly reproducible results.

My project is at [proudindiv/FRBUSinR](https://github.com/proudindiv/FRBUSinR) on [github](https://github.com) with my current results described in the [frbus.pdf](https://docs.google.com/viewer?url=https://raw.githubusercontent.com/proudindiv/FRBUSinR/ReverseEngineer/frbus.pdf) file.  I hope to produce something that attracts others to participate.

### Contents of the FRBUSinR Repository:

1. **frbus_package**, **mce_solve_package**, **state_space_package**, and **data_only_package** contain the contents of the zip files with the FRB/US model downloaded from the Federal Reserve site.
1. **edo_package** contains the contents of the zip file of the Fed's
[Estimated Dynamic Optimization (EDO) Model](https://www.federalreserve.gov/econresdata/edo/edo-models-about.htm),
which I have included as it may have clues to help me with the frbus model.  Unfortunately, the Fed's website points to the wrong file for the the EDO_variable_Listing (ZIP) and it does not seem to be available, so I've included both formats of the EDO paper in the **edo_documentation** directory to use instead.
1. **frbus.nw**, and frbus.pdf which is derived from it, is my first reverse engineering of the variables, equations, and coefficients of the standard version of the model. The frbus.nw noweb file is a literate probram that produces copies of the contents of four of the files in srcEview (stdver_varinfo, stdver_eqs.txt, stdver_coeffs.txt, and variables.txt).
1. **frbuseview.nw**, and frbuseview.pdf which is derived from it, is the start of my second reverse engineering of the model creating copies of all of the Eview program files in the srcEview directory.  This is a very early rough draft and will drastically change as I work on the model.
1. **frbusEDO.Rnw**, and frbusEDO.pdf which is derived from it, contains my analysis of the Fed's EDO model and it's documentation and creates copies of the edo_package files in the srcedo directory.
1. **frbussupport.Rnw**, frbussupport.pdf, **support.nw**, and support.pdf create support files.
1. **frbusdata.Rnw**, and frbusdata.pdf, will study the data used in the model.
1. **frbusmodel.Rnw**, and frbusmodel.pdf, will be my modeling using the Fed's data. which will be derived from it, may possibly be my port of the FRB/US Model in the R programming language.

### Tools Used:

I use TeXstudio and ReText, with noweb and R, on the ubuntu mate operating system:

To compile the noweb .nw files I use this user command in TeXstudio:

```
noweb %.nw | pdflatex -synctex=1 -interaction=nonstopmode %.tex
```

To compile the knitr .Rnw files I use this user command in TeXstudio:

```
Rscript -e "library(knitr);knit('%.Rnw')" | pdflatex -synctex=1 -interaction=nonstopmode %.tex
```

### Web References to Release of the FRB/US Model:

* [Board of Governors of the Federal Reserve System: FRB/US Model](http://www.federalreserve.gov/econresdata/frbus/us-models-about.htm)
* [Stephen Williamson: The FRB/US Model and Inflation](http://newmonetarism.blogspot.com/2014/04/the-frbus-model-and-inflation.html)
* [John B. Taylor: Transparency for Policy Wonk](https://economicsone.com/2014/04/05/transparency-for-policy-wonks/)
* [Noahpinion: The foxy Fed](http://noahpinionblog.blogspot.com/2014/04/the-foxy-fed_7.html)
* [Jon Hilsenrath WSJ: The Fed Wants to Introduce You to Its Friend Ferbus](http://blogs.wsj.com/economics/2014/04/03/the-fed-wants-to-introduce-you-to-its-friend-ferbus/)

