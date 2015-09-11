FROM upclose/python3

RUN apk-install \
    python3-dev \
    binutils \
    libc-dev \
    gcc \
    fortify-headers \
  && pip3 install --no-cache virtualenv

# installing certifi fixes OpenSSL 1.0.2 issues with some certificates
RUN virtualenv /wheel_venv && /wheel_venv/bin/pip install certifi
