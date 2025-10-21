FROM python:3.13.9-slim

WORKDIR /usr/src/app

RUN pip install --upgrade pip

RUN pip install --no-cache-dir magic-wormhole-mailbox-server

EXPOSE 4000

CMD [ "twist", "wormhole-mailbox","--usage-db=usage.sqlite" ]