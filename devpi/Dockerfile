FROM upclose/python

RUN virtualenv /devpi-venv
RUN /devpi-venv/bin/pip --no-cache-dir install devpi-server==2.2.2

ENTRYPOINT ["/devpi-venv/bin/devpi-server", "--serverdir=/data", "--host=0.0.0.0"]
