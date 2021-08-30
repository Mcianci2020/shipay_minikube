FROM python:3.8-slim-buster

RUN apt -y update && apt -y install curl \
    && curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash \
    && curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.19.0/bin/linux/amd64/kubectl \
    && chmod +x ./kubectl && mv ./kubectl /usr/local/bin/kubectl

WORKDIR /app/current

COPY . .

RUN chmod +x deploy.sh

CMD [ "sh","/app/current/deploy.sh" ]
