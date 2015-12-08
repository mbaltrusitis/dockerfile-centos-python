FROM mbaltrusitis/centos-python:3.4

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

ONBUILD COPY requirements.txt /usr/src/app/
ONBUILD RUN pip3 install --no-cache-dir -r requirements.txt

ONBUILD COPY . /usr/src/app