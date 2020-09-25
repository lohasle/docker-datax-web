FROM openjdk:8-alpine
MAINTAINER lohasle
WORKDIR /opt/datax

RUN set -xe \
    && apk add --no-cache curl python2 tar \
    && curl -sSL http://datax-opensource.oss-cn-hangzhou.aliyuncs.com/datax.tar.gz | tar xz --strip 1 \
    && bin/datax.py --help \
    && apk del curl tar

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

ENV PATH=/opt/datax/bin:$PATH

ENTRYPOINT ["datax.py"]
CMD ["--help"]
