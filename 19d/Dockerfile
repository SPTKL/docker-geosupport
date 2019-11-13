FROM continuumio/miniconda3:4.6.14

USER root 

RUN apt update\
    && apt install -y\
    curl git unzip

WORKDIR /var/geocode

COPY linux_geo19d_19.4.zip .
RUN unzip *.zip\
    && rm *.zip

ENV GEOFILES=/var/geocode/version-19d_19.4/fls/
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/var/geocode/version-19d_19.4/lib/

RUN conda install -c conda-forge gdal
RUN pip install python-geosupport pandas sqlalchemy psycopg2-binary usaddress
