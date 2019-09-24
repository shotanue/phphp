FROM alpine:3.10.2 AS work

RUN apk update && apk add --no-cache tzdata

FROM alpine:3.10.2 AS app

COPY --from=work /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN apk update && apk add --no-cache \
        composer \
        php7 \
        php7-pdo

WORKDIR /var/www/app
COPY app .

VOLUME /var/www/app

#ENTRYPOINT [""]
#CMD [""]