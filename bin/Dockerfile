FROM oraclelinux:7-slim

RUN mkdir /operator

COPY triplea-operator /operator/

WORKDIR /operator

RUN chmod u+x /operator/triplea-operator

RUN curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"

RUN chmod +x ./kubectl

RUN mv ./kubectl /usr/local/bin/kubectl

ENTRYPOINT ["/operator/triplea-operator"]

