FROM dazworrall/jenkins-slave
MAINTAINER Darren Worrall, darren@iweb.co.uk

RUN apt-get update
RUN apt-get install -qy --no-install-recommends curl
RUN curl -sL https://deb.nodesource.com/setup_5.x | sudo bash -
RUN apt-get install -qy nodejs

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
