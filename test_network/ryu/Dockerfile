FROM ubuntu

Maintainer Murat Parlakisik <parlakisik@gmail.com>

ENV HOME /root
WORKDIR /root

RUN apt-get update && \
          apt-get install -qy python-setuptools python-pip curl gcc python2-dev \
          libffi-dev libssl-dev libxml2-dev libxslt1-dev zlib1g-dev git && \
          apt-get install -qy python-setuptools && \
          apt-get install -qy pip && \
          pip install ryu


EXPOSE  6633 

