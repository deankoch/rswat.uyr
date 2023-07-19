
<!-- README.md is generated from README.Rmd. Please edit that file -->

# rswat.maker

An R package for building QSWAT+ inputs and creating SWAT+ projects

<!-- badges: start -->
<!-- badges: end -->

## Installation

You can install the development version of rswat.maker like so:

``` r
devtools::install_github('deankoch/rswat.maker')
```

## Background

A number of different earth sciences datasets are needed to initialize a
SWAT+ model:

- landscape feature polygons - including an AOI and the water bodies in
  it
- digital elevation model raster (DEM)
- land use raster (and lookup table)
- soils classification raster (and lookup table)
- stream flow time series

rswat.maker takes an outlet location of interest, finds the
corresponding watershed area, then downloads and processes the required
datasets from public sources. It produces a set of output files ready
for QSWAT+, and retains copies of the source datasets for later use.
Then it uses `shell` to run QSWAT+, followed by SWAT+ Editor. The result
is a SWAT+ model directory that is ready for training.

rswat.maker is primarily a data-retrieval package, so it can also be
useful to hydrologists and earth systems modelers who aren’t interested
in the SWAT+ simulator. rswat.maker is connected to rswat in that it
serves as a source of example data, and we use both tools together in
our project. However, with the exception of `write_wx`, rswat.maker does
not depend on rswat. In fact, users can run most of the workflow in
rswat.maker (all but the last three steps) without touching SWAT+ or its
helper software.

## History

rswat.maker is largely based on code in the URYW_data repository, now
much simplified so that it can be maintained as a self-contained R
package.

Our watershed of interest is the Upper Yellowstone, so most of the
testing in rswat.maker has focused on areas upstream of Carter’s Bridge,
Montana (near Livingston). This includes Paradise Valley and most of
Yellowstone National Park. In the vignette we look at one its
tributaries, the Lamar River.

## Motivation

The purpose of rswat.maker is to automate and document ETL for the
datasets required by QSWAT+ when creating any new SWAT+ model. This is
part of a larger effort to create reproducible workflows for SWAT+
simulations in research

The package helps us manage a freshwater forecasting system for the
Upper Yellowstone River (UYR) watershed based around SWAT+ simulations.

## Development to-do list

- CRAN checks
- Lamar River vignette
