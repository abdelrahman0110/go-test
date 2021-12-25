FROM golang:1.16-alpine3.14 AS builder

WORKDIR /app

COPY . /app

RUN go build -o main main.go


FROM alpine:3.14

WORKDIR /app

COPY --from=builder /app/main .


CMD [ "/app/main" ]
