FROM ubuntu

RUN apt-get update && apt-get upgrade -y
RUn apt-get install -y nodejs npm git vim emacs

RUN npm install yarn --global && npm install npm --global

# docker build -t my-yarn .
# docker run -it --rm my-yarn