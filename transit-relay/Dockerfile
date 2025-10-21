FROM python:3.13.9-slim

WORKDIR /usr/src/app

RUN pip install --upgrade pip

RUN pip install --no-cache-dir magic-wormhole-transit-relay

EXPOSE 4001

CMD ["twist", "transitrelay"]