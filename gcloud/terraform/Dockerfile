FROM google/cloud-sdk

ENV TERRAFORM_VERSION=0.11.9
ENV TERRAFORM_SHA256SUM=5d674e7b83945c37f7f14d0e4f655787dad86ba15b26e185604aa0c3812394ab
ENV TERRAFORM_URL=https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y unzip

RUN curl -O ${TERRAFORM_URL} && \
    echo "${TERRAFORM_SHA256SUM}  terraform_${TERRAFORM_VERSION}_linux_amd64.zip" > terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    sha256sum -c --strict terraform_${TERRAFORM_VERSION}_SHA256SUMS && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip -d /usr/local/bin && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip
