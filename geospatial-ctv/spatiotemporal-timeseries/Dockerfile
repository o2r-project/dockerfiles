FROM o2rproject/geospatial-ctv:spatiotemporal

LABEL maintainer "daniel.nuest@uni-muenster.de"

## Install R packages from CRAN task view TimeSeries
RUN install2.r --error \
    ctv \
  # takes too long, build gets canceled on Docker Hub:
  && R -e "ctv::install.views('TimeSeries'); warnings()"

# Metadata http://label-schema.org/rc1/
LABEL org.label-schema.vendor="o2r project" \
      org.label-schema.url="https://github.com/o2r-project/dockerfiles/" \
      org.label-schema.name="CRAN Task Views 'Spatial', 'SpatioTemporal', and 'TimeSeries'" \
      org.label-schema.description="Extending rocker/geospatial with the full CRAN Task Views for Spatial, SpatioTemporal, and TimeSeries packages" \    
      org.label-schema.vcs-url=$VCS_URL \
      org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.docker.schema-version="rc1"

# docker build --tag geospatial-ctv-st-ts .
# docker run geospatial-ctv-st-ts R