#official image
FROM python:3.8.3-alpine

#set workdir
WORKDIR /usr/src/app

#set variables enviropment
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

#install psycopg2 dependencies
RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev

#install dependences 
RUN pip install --upgrade pip
COPY ./requirements.txt ./
RUN pip3 install -r requirements.txt --no-cache-dir

#copy entrypint.sh
COPY ./entrypoint.sh ./

#copy project
COPY ./ ./

#run entrypoint.sh
ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]