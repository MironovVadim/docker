
FROM python:3.6.0-alpine
WORKDIR /app
ADD requirements.txt /app
RUN pip install -r requirements.txt
ADD . /app
EXPOSE  5000

ENV POST_DATABASE_HOST mongodb

ENTRYPOINT ["python3", "post_app.py"]