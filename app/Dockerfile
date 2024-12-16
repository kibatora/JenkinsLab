FROM python:3.9-slim-buster

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

RUN curl -fsSL https://get.docker.com | sh

COPY . .

CMD ["python", "app.py"]

