FROM java:8

MAINTAINER Sean Li <mail@shang.li>

# Install

WORKDIR /

COPY orientdb-community-2.0.6.tar.gz /

RUN mkdir -p /opt/orient && \
  tar -zxvf orientdb-community-2.0.6.tar.gz --strip-components=1 --directory /opt/orient && \
  rm -rf orientdb-community-2.0.6.tar.gz

# Configs

RUN rm -rf /opt/orient/config

ADD conf/* /opt/orient/config/

# Expose the necessary ports

EXPOSE 2424 2480 5701

# Setup default environment

ENV IP=0.0.0.0 TCP=true AWS=false AWS_ACCESS_KEY=NOTSET AWS_SECRET_KEY=NOTSET AWS_REGION=eu-west-1 AWS_SECURITY_GROUP=core MEMBERS=0.0.0.0

# Set the default command

CMD /opt/orient/config/orient.sh
