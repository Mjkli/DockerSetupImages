FROM alpine

RUN apk update
RUN apk add curl

RUN wget https://releases.hashicorp.com/terraform/1.5.4/terraform_1.5.4_linux_amd64.zip
RUN unzip terraform_1.5.4_linux_amd64.zip
RUN mv terraform /usr/bin/terraform


RUN apk add py3-pip gcc musl-dev python3-dev libffi-dev openssl-dev cargo make docker openrc
RUN pip install --upgrade pip
RUN pip install awscli
