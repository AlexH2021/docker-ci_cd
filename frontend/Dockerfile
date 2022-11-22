FROM nginx:latest

ARG BACKEND_URL
ARG backend

WORKDIR /app/src
RUN apt update && apt install -y unzip
COPY ../acit4640-py-mysql-master.zip /tmp/source.zip
RUN unzip /tmp/source.zip && cp -a acit4640-py-mysql-master/frontend/. /app/src/ && rm -rf acit4640-py-mysql-master

COPY templates /etc/nginx/templates/

RUN service nginx restart