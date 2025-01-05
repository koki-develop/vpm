FROM thevlang/vlang:alpine
WORKDIR /app

RUN apk add make libpq-dev
RUN v up

COPY v.mod v.mod
RUN v install

COPY . .

CMD ["v", "run", "."]
