# This Dockerfile builds the docker image used for running circle ci tests.
# We need terraform installed for our full test suite so it installs that.
# It's updated by running make build-testing-image
FROM circleci/golang:1.10

# Install Terraform
ENV TERRAFORM_VERSION=0.11.7
RUN curl -LOks https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    sudo mkdir -p /usr/local/bin/tf/versions/${TERRAFORM_VERSION} && \
    sudo unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip -d /usr/local/bin/tf/versions/${TERRAFORM_VERSION} && \
    sudo ln -s /usr/local/bin/tf/versions/${TERRAFORM_VERSION}/terraform /usr/local/bin/terraform && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip