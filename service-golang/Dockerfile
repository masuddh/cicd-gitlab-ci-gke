FROM golang:1.18-alpine as builder

WORKDIR /app
COPY ./service-golang .

RUN apk --no-cache add git
RUN go mod tidy 
RUN go build -o main main.go

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /app/main .

CMD ["./main"]
