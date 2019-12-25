FROM alpine

LABEL maintainer="soyster@student.21-school.ru"

RUN apk update && \
    apk upgrade && \
    apk add vim

ENTRYPOINT vim

# docker build .
# docker run -it id