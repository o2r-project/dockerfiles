# dockerfiles

Dockerfiles for base images for [executable research containers (ERC)](http://o2r.info/erc-spec) and for use in the [o2r microservice architecture](http://o2r.info/architecture/).

## geospatial-ctv

This image comes in three layers, each extending the previous one and installing one [CRAN Task View]().

- `o2rproject/geospatial-ctv:spatial`
- `o2rproject/geospatial-ctv:spatiotemporal`
- `o2rproject/geospatial-ctv:spatiotemporal-timeseries`

### `spatial`

[![license](https://img.shields.io/badge/license-Apache-2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [![](https://images.microbadger.com/badges/image/o2rproject/geospatial-ctv.svg)](https://microbadger.com/images/o2rproject/geospatial-ctv)  [![](https://img.shields.io/docker/pulls/o2rproject/geospatial-ctv.svg)](https://hub.docker.com/r/o2rproject/geospatial-ctv) [![](https://img.shields.io/docker/automated/o2rproject/geospatial-ctv.svg)](https://hub.docker.com/r/o2rproject/geospatial-ctv/builds)

Extends the image [`rocker/geospatial`](https://hub.docker.com/r/rocker/geospatial/) with the full tasks views [Spatial](https://cran.r-project.org/web/views/Spatial.html), [SpatioTemporal](https://cran.r-project.org/web/views/SpatioTemporal.html), and [TimeSeries](https://cran.r-project.org/web/views/TimeSeries.html).


### `spatiotemporal`

Currently **missing packages** which could not be installed from the task view:

- `rpanel` ([tcl] can't find package BWidget.)
- `lgcp` (depends on `rpanel`)
- `tkrplot` (tcltkimg.c:2:16: fatal error: tk.h: No such file or directory)
- `RPyGeo` (package ‘RPyGeo’ is not available (for R version 3.4.0))
- `rJava` (error: Java interpreter '/usr/bin/java' does not work)
- `adehabitat` (depends on `tkrplot`)
- `spcosa` (depends on `rJava`)
- `OpenStreetMap` (depends on `rJava`)
- `spatsurv` (depends on `OpenStreetMap`)

### `spatiotemporal-timeseries`

Currently **missing packages** which could not be installed from the task view:

- `rpanel` ([tcl] can't find package BWidget.)
- `RGtk2` (configure: error: GTK version 2.8.0 required)
- `cairoDevice` (ERROR: gtk+2.0 not found by pkg-config.)
- `SDD` (depends on `rpanel`)
- `x12GUI` (depends on `RGtk2`, `cairoDevice`)

## geospatial-containerit

Extending the image `geospatial-ctv:spatiotemporal-timeseries` with [`containerit`](https://github.com/o2r-project/containerit/) to have a good image while running submitted workspaces in `o2r-loader`.