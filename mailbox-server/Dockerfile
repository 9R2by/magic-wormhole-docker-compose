FROM python:3.13.9-slim

ARG USERNAME=peter
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

WORKDIR "/home/${USERNAME}"

RUN pip install --upgrade pip

RUN pip install --no-cache-dir magic-wormhole-mailbox-server

USER $USERNAME

EXPOSE 4000

CMD [ "twist", "wormhole-mailbox","--usage-db=usage.sqlite" ]