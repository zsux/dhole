#!/usr/bin/env bash
mkdir -p /root/.ssh
echo "
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDc9YDspihwMmV75SmthLg72Wkj5RMkG9MzS3XX4aM2l+L487xDLaYjQVj6k4L2w+WQ2fsjLORMsd9Hivbggo3IdJBptOSMi5xyRIBEzY/evQdzhOfhPvq+y/r6P2o67reKMN1+/qclpfstZxQvrZz7QCOTYkCYPCTbX52HNSEg4BfpmZlVpC2Rb47ZszyzMfviH/GBVodDvfen0RwofX8loMDiFGVJseeoGrtUALQp88veFJHyUt9w9pFcuucz36BE9pm6NGj/Jnm4KluNIIhyi0kcPdzsVSdyEP7LmnkurfLE3r3gR62nQwOWh3ZegSG0APBWIhtVTtV8ITALBuvF barry@mac
" > /root/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
