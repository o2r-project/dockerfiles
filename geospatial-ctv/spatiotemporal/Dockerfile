FROM o2rproject/geospatial-ctv:spatial

LABEL maintainer "daniel.nuest@uni-muenster.de"

## Install R packages from taskviews SpatioTemporal
RUN install2.r --error \
    ctv \
  && R -e "ctv::install.views('SpatioTemporal'); warnings()"

# Metadata http://label-schema.org/rc1/
LABEL org.label-schema.vendor="o2r project" \
      org.label-schema.url="https://github.com/o2r-project/dockerfiles/" \
      org.label-schema.name="CRAN Task Views 'Spatial' and 'SpatioTemporal'" \
      org.label-schema.description="Extending rocker/geospatial with the full CRAN Task Views for Spatial and SpatioTemporal packages" \    
      org.label-schema.vcs-url=$VCS_URL \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.docker.schema-version="rc1"

# docker build --tag geospatial-ctv-st .
# docker run geospatial-ctv-st R