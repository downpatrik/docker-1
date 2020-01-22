FROM debian

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak
EXPOSE 9987/udp 10011 30033

ARG TEAMSPEAK_CHECKSUM=18c63ed4a3dc7422e677cbbc335e8cbcbb27acd569e9f2e1ce86e09642c81aa2
ARG TEAMSPEAK_URL=https://files.teamspeak-services.com/releases/server/3.11.0/teamspeak3-server_linux_amd64-3.11.0.tar.bz2

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y wget bzip2
RUN wget "${TEAMSPEAK_URL}" -O server.tar.bz2
RUN echo "${TEAMSPEAK_CHECKSUM} *server.tar.bz2" | sha256sum -c -;
RUN tar -xvf server.tar.bz2
RUN rm server.tar.bz2

WORKDIR teamspeak3-server_linux_amd64
ENTRYPOINT sh ts3server_minimal_runscript.sh

# docker build -t ex01 .
# docker run -d --name teamspeak --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01