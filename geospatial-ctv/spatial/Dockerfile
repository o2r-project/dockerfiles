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

# Metadata http://label-schema.org/rc1/
LABEL org.label-schema.vendor="o2r project" \
      org.label-schema.url="https://github.com/o2r-project/dockerfiles/" \
      org.label-schema.name="CRAN Task View 'Spatial'" \
      org.label-schema.description="Extending rocker/geospatial with the full CRAN Task View for Spatial packages" \    
      org.label-schema.vcs-url=$VCS_URL \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.docker.schema-version="rc1"

# docker build --tag geospatial-ctv-spatial .
# docker run geospatial-ctv-spatial R