FROM python:3.10-slim-buster

# Upgrade pip and install Python dependencies
RUN pip install --upgrade pip

RUN apt-get update && apt-get install -y \
    wget \
    nginx \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install flask gevent gunicorn pandas dill

ENV PYTHONUNBUFFERED=TRUE
ENV PYTHONDONTWRITEBYTECODE=TRUE 
ENV PATH="/opt/program:${PATH}"

# Copy the directory 'script' which contains our script file to the /opt/program directory of the image.
COPY Files /opt/program  

WORKDIR /opt/program