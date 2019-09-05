FROM continuumio/miniconda3:4.6.14

USER root

RUN apt update\
    && apt install -y\
    curl git unzip

WORKDIR /var/geocode

RUN curl -O https://www1.nyc.gov/assets/planning/download/zip/data-maps/open-data/gdelx_18a.zip\
    && unzip *.zip\
    && rm *.zip

ENV GEOFILES=/var/geocode/version-18a_18.1/fls/
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/var/geocode/version-18a_18.1/lib/

RUN pip install --upgrade pip\
    && pip install python-geosupport