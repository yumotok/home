FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-22.04

# Clean up old resources
RUN rm -Rf /current/aws 

RUN mkdir -p /current/aws
WORKDIR /current/aws

RUN apt update && apt install -y wget unzip curl

# Install Terraform
RUN wget https://releases.hashicorp.com/terraform/1.8.5/terraform_1.8.5_linux_amd64.zip && \
    unzip terraform_1.8.5_linux_amd64.zip && \
    mv terraform /usr/local/bin/terraform && \
    rm terraform_1.8.5_linux_amd64.zip

# Install AWS CLI
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
    unzip awscliv2.zip && \
    sudo ./aws/install && \
    rm awscliv2.zip
