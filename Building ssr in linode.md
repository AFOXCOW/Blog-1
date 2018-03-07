# Shadowsocks installation
##  install wget
    yum install -y wget
## install shadowsocks
    wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
    chmod +x shadowsocks-all.sh
    ./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
## install ServerSpeeder
```wget -N --no-check-certificate https://github.com/91yun/serverspeeder/raw/master/serverspeeder.sh && bash serverspeeder.sh```
## or install BBR
```wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
    reboot```
## check whether installed successfully
```lsmod | grep bbr```
## if bbr exists in the result, install successfully
# SSR for multiusers
## install pip and git 
    yum install -y python-setuptools && easy_install pip
    yum install -y git
## clone source codes
    git clone -b manyuser https://github.com/shadowsocksrr/shadowsocksr.git
## server configuration
    cd ~/shadowsocksr
    bash initcfg.sh
## modify the ```userapiconfig.py``` as follows
    API_INTERFACE = 'mudbjson' #modify interface type
    SERVER_PUB_ADDR = '127.0.0.1' #modify the public network IP corresponding to the generated link
## add a new user
    python mujson_mgr.py -a -u test -p 20180  -k li9816 -m aes-256-cfb -O auth_chain_a -o tls1.2_ticket_auth
## run server with log
    ./logrun.sh
## if dont need log
    ./run.sh

