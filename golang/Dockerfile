FROM golang:latest AS build

WORKDIR /app

COPY go.mod ./

RUN go mod download

COPY . .

RUN go build -o build/fizzbuzz

FROM gcr.io/distroless/base-debian11

COPY --from=build /app/build/fizzbuzz /

COPY --from=build /app/templates/index.html /templates/

CMD ["/fizzbuzz", "serve"]