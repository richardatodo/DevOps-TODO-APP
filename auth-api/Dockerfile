FROM golang:1.18 AS build
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o auth-api

FROM alpine
WORKDIR /root/
COPY --from=build /app/auth-api .
CMD ["./auth-api"]
EXPOSE 8080