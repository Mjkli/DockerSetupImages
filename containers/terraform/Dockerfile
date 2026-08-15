FROM alpine

RUN apk add --no-cache curl wget unzip

RUN wget https://releases.hashicorp.com/terraform/1.9.2/terraform_1.9.2_linux_amd64.zip
RUN unzip terraform_1.9.2_linux_amd64.zip
RUN mv terraform /usr/bin/terraform

RUN apk add py3-pip gcc musl-dev python3-dev libffi-dev openssl-dev cargo make docker openrc
RUN python3 -m venv /opt/venv

ENV PATH="/opt/venv/bin:$PATH"

RUN pip install --upgrade pip \
    && pip install awscli
