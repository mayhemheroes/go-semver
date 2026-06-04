FROM golang:1.21 AS builder

WORKDIR /src
COPY . /src/go-semver
WORKDIR /src/go-semver
RUN go test -c -fuzz=FuzzNewVersion -o /string-fuzz.libfuzzer .

FROM ubuntu:20.04
COPY --from=builder /string-fuzz.libfuzzer /string-fuzz.libfuzzer
