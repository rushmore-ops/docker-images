FROM ubuntu:14.04

RUN locale-gen en_US.UTF-8 && \
    echo 'LANG="en_US.UTF-8"' > /etc/default/locale

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8

# Postgresql installation
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main" > /etc/apt/sources.list.d/pgdg.list
RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive \
    apt-get install -y --force-yes --no-install-recommends \
        postgresql-9.3 postgresql-client-9.3 postgresql-contrib-9.3 \
        postgresql-9.3-postgis-2.1 postgresql-server-dev-9.3
RUN /etc/init.d/postgresql stop

#Helper tools
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends inotify-tools

# required to ensure that we can insert a userid intodb
RUN chmod a+w /etc/passwd

CMD ["/host/postgresql/scripts/start"]
