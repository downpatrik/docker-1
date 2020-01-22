FROM alpine

RUN apk update && apk upgrade
RUN apk add vim

ENTRYPOINT vim

# we must go to the folder with the file through the terminal
# docker build -t image-name -> docker build -t ex00 .
# dokcer run --rm -it image-name -> docker run --rm -it ex00