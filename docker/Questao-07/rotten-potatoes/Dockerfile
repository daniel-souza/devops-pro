FROM python:3.7-alpine

WORKDIR /app

RUN apk add jpeg-dev zlib-dev gcc musl-dev
# RUN apt-get upodate && \\
    # apt-get install libjpeg8-dev zlib1g-dev

COPY ./src/requirements.txt .
RUN pip3 install --upgrade pip && \
    pip3 install -r requirements.txt

COPY ./src .

ARG MONGODB_DB=admin
ARG MONGODB_HOST=localhost
ARG MONGODB_PORT=27017
ARG MONGODB_USERNAME=mongouser
ARG MONGODB_PASSWORD=mongopwd

ENV MONGODB_DB=$MONGODB_DB
ENV MONGODB_HOST=$MONGODB_HOST
ENV MONGODB_PORT=$MONGODB_PORT
ENV MONGODB_USERNAME=$MONGODB_USERNAME
ENV MONGODB_PASSWORD=$MONGODB_PASSWORD

RUN export FLASK_APP=app.py
EXPOSE 5000

CMD ["sh", "-c",  "python3 -c \
            'from config import on_starting; on_starting(None)'\
            && flask run --host=0.0.0.0"]