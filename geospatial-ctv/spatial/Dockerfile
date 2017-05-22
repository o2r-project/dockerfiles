FROM rocker/geospatial:latest

LABEL maintainer "daniel.nuest@uni-muenster.de"

## Install R packages from CRAN task view Spatial
## (rocker/geospatial only contains "core" packages from Spatial) 
RUN  apt-get update \
  && apt-get install -y --no-install-recommends \
    # for protolite
    libprotobuf-dev \
    protobuf-compiler \
    # for V8
    libv8-3.14-dev \
  && apt-get autoremove -y \
  && apt-get autoclean -y \
  && rm -rf /var/lib/apt/lists/*

RUN install2.r --error \
    ctv \
  && R -e "ctv::install.views('Spatial'); warnings()"

# docker build --tag geospatial-ctv-spatial .
# docker run geospatial-ctv-spatial R