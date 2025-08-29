FROM ubuntu:24.04
LABEL maintainer="yofranky"
ENV DEBIAN_FRONTEND=noninteractive
WORKDIR /home/lab

# Install base + networking + CI/CD tools in one go
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y \
        curl vim unzip wget sudo bash-completion ca-certificates gnupg \
        software-properties-common lsb-release \
        tcpdump nload iproute2 net-tools dnsutils iputils-ping traceroute nmap \
        git make \
    && rm -rf /var/lib/apt/lists/*

# Install HashiCorp tools (pinned versions)
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg && \
    echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
    https://apt.releases.hashicorp.com $(lsb_release -cs) main" \
    | tee /etc/apt/sources.list.d/hashicorp.list && \
    apt-get update && \
    apt-get install -y terraform=1.9.8 packer=1.11.2 && \
    rm -rf /var/lib/apt/lists/*

# Optional: create non-root user
RUN useradd -ms /bin/bash labuser && \
    echo "labuser ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER labuser

CMD ["/bin/bash"]
