<!-- README.md is generated from README.Rmd. Please edit that file - rmarkdown::render('README.Rmd', output_format = 'md_document', output_file = 'README.md') -->
Geocomputation with R
=====================

[![Build Status](https://travis-ci.org/Robinlovelace/geocompr.svg?branch=master)](https://travis-ci.org/Robinlovelace/geocompr)

Introduction
============

This repository hosts the code underlying Geocomputation with R, a book by [Robin Lovelace](http://robinlovelace.net/) and [Jakub Nowosad](https://nowosad.github.io/).

The online version of the book is developed at <http://robinlovelace.net/geocompr/>. We plan to publish the hard copy of the book with CRC Press in 2018.

Contributing
------------

We encourage contributions on any part of the book, including:

-   Improvements to the text, e.g. clarifying unclear sentences, fixing typos (see guidance from [Yihui Xie](https://yihui.name/en/2013/06/fix-typo-in-documentation/)).
-   Changes to the code, e.g. to do things in a more efficient way.
-   Suggestions on content (see the project's [issue tracker](https://github.com/Robinlovelace/geocompr/issues) and the [work-in-progress](https://github.com/Robinlovelace/geocompr/tree/master/work-in-progress) folder for chapters in the pipeline).

Please see [our\_style.md](https://github.com/Robinlovelace/geocompr/blob/master/our_style.md) for the book's style.

Reproducing the book
--------------------

To ease reproducibility, this book is also a package. Installing it from GitHub will ensure all dependencies to build the book are available on your computer (you need [**devtools**](https://github.com/hadley/devtools)):

``` r
devtools::install_github("robinlovelace/geocompr")
```

You need a recent version of the GDAL, GEOS, Proj.4 and UDUNITS libraries installed for this to work on Mac and Linux. See the **sf** package's [README](https://github.com/edzer/sfr) for information on that.

Once the dependencies have been installed you should be able to build and view a local version the book with:

``` r
bookdown::render_book("index.Rmd") # to build the book
browseURL("_book/index.html") # to view it
```

Reproducing this README
-----------------------

To reduce the book's dependencies, scripts to be run infrequently to generate input for the book are run on creation of this README.

The additional packages required for this can be installed as follows:

``` r
pkgs = c("cranlogs", "diagram", "globe")
to_install = !pkgs %in% installed.packages()
if(any(to_install)) {
  install.packages(pkgs[to_install])
}
```

With these additional dependencies installed, you should be able to run the following scripts, which create input figures for the book:

``` r
source("code/cranlogs.R")
source("code/sf-revdep.R")
source("code/sfr-class-diagram-gen.R")
```

Note: the `.Rproj` file is configured to build a website not a single page. To reproduce this [README](https://github.com/Robinlovelace/geocompr/blob/master/README.Rmd) use the following command:

``` r
rmarkdown::render("README.Rmd", output_format = "md_document", output_file = "README.md")
```

Book statistics
---------------

An indication of the book's progress over time is illustrated below (to be updated roughly every week as the book progresses).

![](figures/bookstats-1.png)

Book statistics: estimated number of pages per chapter over time.

Citations
---------

To cite packages used in this book we use code from [Efficient R Programming](https://csgillespie.github.io/efficientR/):

``` r
geocompr:::generate_citations()
```

This generates .bib and .csv files containing the packages. The current list of files used is as follows:

``` r
pkg_df = readr::read_csv("extdata/package_list.csv")
knitr::kable(pkg_df)
```

| Name           | Title                                                                                        | version    |
|:---------------|:---------------------------------------------------------------------------------------------|:-----------|
| bookdown       | Authoring Books and Technical Documents with R Markdown (Xie 2017a)                          | 0.4        |
| dismo          | Species Distribution Modeling (Hijmans et al. 2017)                                          | 1.1.4      |
| gstat          | Spatial and Spatio-Temporal Geostatistical Modelling, Prediction (Pebesma and Graeler 2017)  | 1.1.5      |
| knitr          | A General-Purpose Package for Dynamic Report Generation in R (Xie 2017b)                     | 1.16       |
| leaflet        | Create Interactive Web Maps with the JavaScript 'Leaflet' (Cheng, Karambelkar, and Xie 2017) | 1.1.0      |
| link2GI        | Linking GIS, Remote Sensing and Other Command Line Tools (Reudenbach 2017)                   | 0.1.0      |
| mapview        | Interactive Viewing of Spatial Objects in R (Appelhans et al. 2017)                          | 2.1.4      |
| microbenchmark | Accurate Timing Functions (Mersmann 2015)                                                    | 1.4.2.1    |
| osmdata        | Import 'OpenStreetMap' Data as Simple Features or Spatial (Padgham et al. 2017)              | 0.0.4      |
| raster         | Geographic Data Analysis and Modeling (Hijmans 2016)                                         | 2.5.8      |
| rgdal          | Bindings for the Geospatial Data Abstraction Library (Bivand, Keitt, and Rowlingson 2017)    | 1.2.8      |
| rgeos          | Interface to Geometry Engine - Open Source (GEOS) (Bivand and Rundel 2017)                   | 0.3.23     |
| rmarkdown      | Dynamic Documents for R (Allaire et al. 2017)                                                | 1.6        |
| RQGIS          | Integrating R with QGIS (Muenchow and Schratz 2017)                                          | 1.0.1      |
| RSAGA          | SAGA Geoprocessing and Terrain Analysis in R (Brenning and Bangs 2016)                       | 0.94.5     |
| sf             | Simple Features for R (Pebesma 2017)                                                         | 0.5.4      |
| sp             | Classes and Methods for Spatial Data (Pebesma and Bivand 2017)                               | 1.2.5      |
| spData         | Datasets for Spatial Analysis (Bivand, Nowosad, and Lovelace 2017)                           | 0.2.4.9000 |
| tidyverse      | Easily Install and Load 'Tidyverse' Packages (Wickham 2017)                                  | 1.1.1      |
| tmap           | Thematic Maps (Tennekes 2017)                                                                | 1.11       |

Other citations are stored online using Zotero and downloaded with:

``` r
geocompr:::dl_citations(f = "refs.bib", user = 418217, collection = "9K6FRP6N")
```

If you would like to add to the references, please use Zotero, join the [open group](https://www.zotero.org/groups/418217/energy-and-transport) add your citation to the open [geocompr library](https://www.zotero.org/groups/418217/energy-and-transport/items/collectionKey/9K6FRP6N).

References
----------

Allaire, JJ, Joe Cheng, Yihui Xie, Jonathan McPherson, Winston Chang, Jeff Allen, Hadley Wickham, Aron Atkins, Rob Hyndman, and Ruben Arslan. 2017. *Rmarkdown: Dynamic Documents for R*. <https://CRAN.R-project.org/package=rmarkdown>.

Appelhans, Tim, Florian Detsch, Christoph Reudenbach, and Stefan Woellauer. 2017. *Mapview: Interactive Viewing of Spatial Objects in R*. <https://CRAN.R-project.org/package=mapview>.

Bivand, Roger, and Colin Rundel. 2017. *Rgeos: Interface to Geometry Engine - Open Source (Geos)*. <https://CRAN.R-project.org/package=rgeos>.

Bivand, Roger, Tim Keitt, and Barry Rowlingson. 2017. *Rgdal: Bindings for the Geospatial Data Abstraction Library*. <https://CRAN.R-project.org/package=rgdal>.

Bivand, Roger, Jakub Nowosad, and Robin Lovelace. 2017. *SpData: Datasets for Spatial Analysis*. <https://github.com/Nowosad/spData>.

Brenning, Alexander, and Donovan Bangs. 2016. *RSAGA: SAGA Geoprocessing and Terrain Analysis in R*. <https://CRAN.R-project.org/package=RSAGA>.

Cheng, Joe, Bhaskar Karambelkar, and Yihui Xie. 2017. *Leaflet: Create Interactive Web Maps with the Javascript ’Leaflet’ Library*. <https://CRAN.R-project.org/package=leaflet>.

Hijmans, Robert J. 2016. *Raster: Geographic Data Analysis and Modeling*. <https://CRAN.R-project.org/package=raster>.

Hijmans, Robert J., Steven Phillips, John Leathwick, and Jane Elith. 2017. *Dismo: Species Distribution Modeling*. <https://CRAN.R-project.org/package=dismo>.

Mersmann, Olaf. 2015. *Microbenchmark: Accurate Timing Functions*. <https://CRAN.R-project.org/package=microbenchmark>.

Muenchow, Jannes, and Patrick Schratz. 2017. *RQGIS: Integrating R with Qgis*. <https://CRAN.R-project.org/package=RQGIS>.

Padgham, Mark, Bob Rudis, Robin Lovelace, and Maëlle Salmon. 2017. *Osmdata: Import ’Openstreetmap’ Data as Simple Features or Spatial Objects*. <https://CRAN.R-project.org/package=osmdata>.

Pebesma, Edzer. 2017. *Sf: Simple Features for R*. <https://github.com/r-spatial/sf/>.

Pebesma, Edzer, and Roger Bivand. 2017. *Sp: Classes and Methods for Spatial Data*. <https://CRAN.R-project.org/package=sp>.

Pebesma, Edzer, and Benedikt Graeler. 2017. *Gstat: Spatial and Spatio-Temporal Geostatistical Modelling, Prediction and Simulation*. <https://CRAN.R-project.org/package=gstat>.

Reudenbach, Chris. 2017. *Link2GI: Linking Gis, Remote Sensing and Other Command Line Tools*. <https://CRAN.R-project.org/package=link2GI>.

Tennekes, Martijn. 2017. *Tmap: Thematic Maps*. <https://github.com/mtennekes/tmap>.

Wickham, Hadley. 2017. *Tidyverse: Easily Install and Load ’Tidyverse’ Packages*. <https://CRAN.R-project.org/package=tidyverse>.

Xie, Yihui. 2017a. *Bookdown: Authoring Books and Technical Documents with R Markdown*. <https://CRAN.R-project.org/package=bookdown>.

———. 2017b. *Knitr: A General-Purpose Package for Dynamic Report Generation in R*. <https://CRAN.R-project.org/package=knitr>.