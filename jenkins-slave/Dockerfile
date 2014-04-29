FROM ubuntu:14.04
MAINTAINER Darren Worrall, darren@iweb.co.uk

RUN apt-get update
RUN apt-get install -qy openssh-server
RUN mkdir /var/run/sshd

RUN adduser --system --shell /bin/bash --gecos 'jenkins slave user' --disabled-password --home /home/jenkins jenkins
RUN mkdir -p /home/jenkins/.ssh

RUN echo ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDDC1vro3Q8r9VqsqxqAQWQmf2yZEQS1STChsk/le1OH3C3n+NYiJmaUXVE9HT7nJ5oZON/5Gqzh41aNddBd3peS+WK20dAuYWDH6vbYYxMHDHgUcbosfXWd/h2Hv8XTyyJg8FlFuDKNcY06m8pLoM7w1SNf+EiGZq4R4UK5f54MwVVvUgEMp9qnOyYnAL4qOjIKvrn36Of77RMrmwQVVV2wMS5ydSHwKp3jk35iwjAJ7HUDl22U4uHu4mEha5FnsKIL2zqdi3x8lporWknunzFmLxw4J5I6WKNSCxyMCwEqY6JWY2RpAN+rbeD+ZKBGpeY2WAQnaxpRJDn+W28neQH jenkins@ci > /home/jenkins/.ssh/authorized_keys

RUN chown -R jenkins: /home/jenkins/.ssh
RUN chmod -R u=rwX,go-rwx /home/jenkins/.ssh

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
