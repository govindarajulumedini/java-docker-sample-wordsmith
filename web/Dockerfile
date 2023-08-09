# BUILD
FROM golang:alpine as builder

COPY dispatcher.go .
RUN go build dispatcher.go

# RUN
FROM alpine:3.18.3

EXPOSE 80
CMD ["/dispatcher"]

COPY --from=builder /go/dispatcher /
COPY static /static/
