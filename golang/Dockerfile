FROM golang:latest AS build

WORKDIR /app

COPY go.mod ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 go build -o build/fizzbuzz

FROM scratch

COPY --from=build /app/build/fizzbuzz /

COPY --from=build /app/templates/index.html /templates/

CMD ["/fizzbuzz", "serve"]