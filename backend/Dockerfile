FROM python:latest

RUN apt update && apt install -y python3-dev default-libmysqlclient-dev build-essential
RUN useradd -m -d /app backend
USER backend

WORKDIR /app

RUN cp ../acit4640-py-mysql-master.zip /tmp/source.zip && unzip /tmp/source.zip && cp -r acit4640-py-mysql-master/backend /app/src && rm -rf acit4640-py-mysql-master

RUN python -m pip install -r /app/src/requirements.txt

WORKDIR /app/src

CMD ["/app/.local/bin/gunicorn","wsgi:app", "-b", "0.0.0.0:8080"]