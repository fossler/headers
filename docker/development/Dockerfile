FROM alpine:latest

LABEL org.owasp.oshp.url="https://www.owasp.org/index.php/OWASP_Secure_Headers_Project" \
  org.owasp.oshp.name="Owasp SecureHeaders Project" \
  org.owasp.oshp.description="Front-end from SecureHeaders Project" \
  org.owasp.oshp.version="v3.1.0" \
  org.owasp.oshp.maintainer="alexandre menezes <alexandre.fmenezes@owasp.org>"

ENV APP_DIR /opt/headers

WORKDIR $APP_DIR

COPY . .

RUN apk add --no-cache py2-pip py-setuptools gcc make build-base python2-dev \
  && pip2 install --upgrade pip \
  && pip2 install -r requirements.txt

EXPOSE 5000

ADD docker-entrypoint.sh /docker-entrypoint.sh

VOLUME $APP_DIR

ENTRYPOINT ["/docker-entrypoint.sh"]
