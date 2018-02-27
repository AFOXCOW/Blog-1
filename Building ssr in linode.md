# Log in linode using ssh
## then install wget and shadowsocks
    yum install wget -y
    wget --no-check-certificate -O shadowsocks-go.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-go.sh
    chmod +x shadowsocks-go.sh
    ./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log
