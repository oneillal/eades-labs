FROM golang:1.11-alpine AS build

WORKDIR /src/
COPY main.go go.* /src/
RUN CGO_ENABLED=0 go build -o /bin/doorsync

FROM scratch
COPY --from=build /bin/doorsync /bin/doorsync
ENTRYPOINT ["/bin/doorsync"]
