FROM ubuntu

RUN apt-get update -y && apt-get -y upgrade
RUN apt-get -y install wget openssh-server ca-certificates postfix
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh 
RUN	chmod 777 ./script.deb.sh 
RUN ./script.deb.sh

RUN apt-get install -y tzdata gitlab-ce

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && sleep 2 && gitlab-ctl reconfigure && tail -f /dev/null

# https://docs.gitlab.com/omnibus/README.html#installation-and-configuration-using-omnibus-package
# docker build -t ex03 .
# docker run -it -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03