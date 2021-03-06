FROM python:3

RUN apt-get update -y && \
  apt-get install -y python-pip python-dev

WORKDIR /app

RUN pip install Flask
RUN pip install requests

COPY . .

EXPOSE 5000

CMD ["python", "./app.py"]