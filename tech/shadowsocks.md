# hk ss config

- https://github.com/guolin/shadowsocks-docker

info

- ip:47.91.226.210
- docker run -d -p 99:8388 -e SS_PASSWORD=*** guolin/shadowsocks
    
    
```bash
    apt-get update
    echo "hkss" > /etc/hostname
    reboot
    adduser joseph
    vim /etc/ssh/sshd_config #PermitRootLogin no
    vim /etc/sudoers #joseph    ALL=(ALL:ALL) NOPASSWD:ALL
    su - joseph
    mkdir ~/.ssh
    echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDc9YDspihwMmV75SmthLg72Wkj5RMkG9MzS3XX4aM2l+L487xDLaYjQVj6k4L2w+WQ2fsjLORMsd9Hivbggo3IdJBptOSMi5xyRIBEzY/evQdzhOfhPvq+y/r6P2o67reKMN1+/qclpfstZxQvrZz7QCOTYkCYPCTbX52HNSEg4BfpmZlVpC2Rb47ZszyzMfviH/GBVodDvfen0RwofX8loMDiFGVJseeoGrtUALQp88veFJHyUt9w9pFcuucz36BE9pm6NGj/Jnm4KluNIIhyi0kcPdzsVSdyEP7LmnkurfLE3r3gR62nQwOWh3ZegSG0APBWIhtVTtV8ITALBuvF joseph@com' >> ~/.ssh/authorized_keys
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

