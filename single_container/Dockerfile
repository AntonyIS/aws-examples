FROM python:3.5.1-alpine

RUN apk add --update gcc musl-dev && rm -rf /var/cache/apk/*

COPY . /app

RUN pip install gunicorn
RUN pip install -e /app/.

WORKDIR /app

EXPOSE 5000

CMD ["gunicorn", "-b", "0.0.0.0:5000", "wsgi:app"]