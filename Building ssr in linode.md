# Shadowsocks installation
##  install wget
    yum install -y wget
## install shadowsocks
    wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
    chmod +x shadowsocks-all.sh
    ./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
# SSR for multiusers
## install pip and git 
    yum install -y python-setuptools && easy_install pip
    yum install -y git
## 
