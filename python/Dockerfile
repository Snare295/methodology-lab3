FROM python:3.10-alpine

LABEL maintainer="vladneum@gmail.com"

WORKDIR /app

COPY requirements/backend.in .

RUN pip install --no-cache-dir -r backend.in

RUN apk --no-cache add musl-dev linux-headers g++

RUN pip install numpy==1.22.0

COPY . .

CMD ["uvicorn", "spaceship.main:app", "--host=0.0.0.0", "--port=8080"]