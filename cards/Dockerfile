FROM golang as dev

WORKDIR /work

FROM golang as build

WORKDIR /app
COPY ./* /app/
RUN go build -o app

FROM alpine as runtime
COPY --from=build /app/app /
CMD ./app