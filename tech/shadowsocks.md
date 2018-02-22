# hk ss config

- https://github.com/guolin/shadowsocks-docker

    ip:47.91.226.210
    docker run -d -p 99:8388 -e SS_PASSWORD=*** guolin/shadowsocks
    
    
```bash
    apt-get update
    echo "hkss" > /etc/hostname
    reboot
    adduser joseph
    vim /etc/ssh/sshd_config #PermitRootLogin no
    vim /etc/sudoers #joseph    ALL=(ALL:ALL) NOPASSWD:ALL
    su - joseph
    mkdir ~/.ssh
    echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCYpLkpz26qRNrLqC5/QrcoMKUi0zmvv2eRq5Gkt511zl+6vIy8GBfKyE+gBl9gqjmqgUPPbyhxmk3YYOQuXPPmmm3gS3fRrlvjZVmCnjJlhZ3hvugs3OH7OfzP/IIasECkJlec9RQvaKL0wQA5WP75geEaDPF4ZJKdDc8PDddv/QvGpvyBoVX/GQg5pUj78m2R3s6n4Cj+4qC07+9kqUKmUY5ExXk4HUXZYle+MY4ASNjCPAeG2hnE7cNPPwcoHRcHMlobX6pEkRnZtozjJcpF9svU/8yxUhdpcxomRXP8Cisr0vqIVIaHfOTKLKHIx/S7QQjitHuQwtKX93j0dL4D joseph@Josephs-MacBook-Pro.local' >> ~/.ssh/authorized_keys
    chmod 600 ~/.ssh/authorized_keys


    sudo apt-get install \
        linux-image-extra-$(uname -r) \
        linux-image-extra-virtual

    sudo apt-get update
    sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    sudo apt-key fingerprint 0EBFCD88
    sudo add-apt-repository \
        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) \
        stable"
    sudo apt-get update
    sudo apt-get install docker-ce
    apt-cache madison docker-ce
    sudo usermod -aG docker joseph
```


    apt-get update
    echo "xjb" > /etc/hostname
    reboot
    adduser joseph
    vim /etc/ssh/sshd_config #PermitRootLogin no
    vim /etc/sudoers #joseph    ALL=(ALL:ALL) NOPASSWD:ALL
    su - joseph
    mkdir ~/.ssh
    echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCYpLkpz26qRNrLqC5/QrcoMKUi0zmvv2eRq5Gkt511zl+6vIy8GBfKyE+gBl9gqjmqgUPPbyhxmk3YYOQuXPPmmm3gS3fRrlvjZVmCnjJlhZ3hvugs3OH7OfzP/IIasECkJlec9RQvaKL0wQA5WP75geEaDPF4ZJKdDc8PDddv/QvGpvyBoVX/GQg5pUj78m2R3s6n4Cj+4qC07+9kqUKmUY5ExXk4HUXZYle+MY4ASNjCPAeG2hnE7cNPPwcoHRcHMlobX6pEkRnZtozjJcpF9svU/8yxUhdpcxomRXP8Cisr0vqIVIaHfOTKLKHIx/S7QQjitHuQwtKX93j0dL4D joseph@Josephs-MacBook-Pro.local' >> ~/.ssh/authorized_keys
    chmod 600 ~/.ssh/authorized_keys

    sudo apt-get install \
        linux-image-extra-$(uname -r) \
        linux-image-extra-virtual

    sudo apt-get update
    sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    sudo apt-key fingerprint 0EBFCD88
    sudo add-apt-repository \
        "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
        $(lsb_release -cs) \
        stable"
    sudo apt-get update
    sudo apt-get install docker-ce
    apt-cache madison docker-ce
    sudo usermod -aG docker joseph


    sudo curl -L http://47.91.226.210/down/docker-compose -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    docker-compose --version
