FROM ubuntu:18.04

RUN apt-get update

RUN apt-get install --yes \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common \
    wget \
    sudo

# Install python
RUN apt-get install --no-install-recommends --yes python3

# Install Docker
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
RUN apt-get update && apt-get install --yes docker-ce docker-ce-cli containerd.io

# Install k8s
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add
RUN apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"
RUN apt-get update && apt-get install --yes kubeadm kubelet kubectl && apt-mark hold kubeadm kubelet kubectl

# Install kind
RUN curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.9.0/kind-linux-amd64 && chmod +x ./kind && mv ./kind /bin

CMD tail -f /dev/null