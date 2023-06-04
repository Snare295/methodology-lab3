FROM dart:latest

LABEL maintainer="vladneum@gmail.com"

WORKDIR /app

COPY pubspec.yaml .

RUN dart pub get

COPY . .

RUN dart pub get --offline

RUN dart compile exe ./bin/lab3.dart

CMD ["/app/bin/lab3.exe"]