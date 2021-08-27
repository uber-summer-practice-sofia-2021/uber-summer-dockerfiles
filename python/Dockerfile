FROM python:3.8-slim

RUN apt-get update && apt-get install -y vim curl

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY src/ .

EXPOSE 5000
ENV FLASK_ENV=development
ENV FLASK_APP=server.py

CMD ["flask", "run", "--host=0.0.0.0"]
