FROM alpine

RUN apk update

RUN wget https://releases.hashicorp.com/packer/1.9.2/packer_1.9.2_linux_amd64.zip
RUN unzip packer_1.9.2_linux_amd64.zip
RUN mv packer /usr/bin/packer


RUN apk add py3-pip gcc musl-dev python3-dev libffi-dev openssl-dev cargo make docker openrc
RUN pip install --upgrade pip
RUN pip install awscli