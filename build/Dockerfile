# Start by building the application.
FROM golang:1.21 as build

WORKDIR /go/src/app
COPY . .

RUN go mod download
RUN CGO_ENABLED=0 go build -o /go/bin/tftools

# Distroless for production deployments
FROM gcr.io/distroless/static-debian11 as production
COPY --from=build /go/bin/tftools /
ENTRYPOINT ["/tftools"]
