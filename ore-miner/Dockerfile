FROM alpine:edge
MAINTAINER "Evan" <OiCKilL>
RUN echo http:"//dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
  apk update && apk upgrade && apk add \
  gcc musl-dev nano cargo curl 
RUN echo -ne '\n' | curl https://sh.rustup.rs -sSf | export PATH=/root/.cargo/bin:$PATH && cargo install ore-cli
RUN rm -rf /var/lib/apt/lists/*
COPY mine.sh /root/mine.sh
COPY wallet.json /root/wallet.json
ENTRYPOINT ["sh", "/root/mine.sh"]
