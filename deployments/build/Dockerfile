FROM golang:1.23 AS builder

ENV CGO_ENABLED=0

WORKDIR /app

COPY . .

RUN make dep
RUN make -B build


FROM scratch

COPY --from=builder /app/bin/pinger /

CMD ["/pinger"]
