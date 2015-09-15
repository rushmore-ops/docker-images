FROM upclose/python3

# make is only needed for gevent from github checkout
# cython only to build gevent from github
RUN wget -qO- https://github.com/Rushmorefm/alpine-packages/releases/download/v0.2/testing.tar.xz | tar xJ  \
  && apk --allow-untrusted -X /testing -X http://dl-2.alpinelinux.org/alpine/edge/testing -U add \
    python35-dev \
    binutils \
    libc-dev \
    gcc \
    fortify-headers \
    make \
  && rm -rf /testing /var/cache/apk/* \
  && pip3 install --no-cache virtualenv \
  && pip3 install cython

# installing certifi fixes OpenSSL 1.0.2 issues with some certificates
# custom wheel package needed for Python 3.5 until https://bitbucket.org/pypa/wheel/issues/146/wheel-building-fails-on-cpython-350b3 gets fixed
RUN virtualenv /wheel_venv && /wheel_venv/bin/pip install certifi devpi-client \
    && wget https://nipy.bic.berkeley.edu/scipy_installers/wheel-0.24.0-py2.py3-none-any.whl \
    && /wheel_venv/bin/pip install --upgrade wheel-0.24.0-py2.py3-none-any.whl \
