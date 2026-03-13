FROM jupyter/pyspark-notebook:latest

USER root

RUN apt-get update && apt-get install -y \
    default-jre \
    && rm -rf /var/lib/apt/lists/*

USER jovyan

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt