# filebrowser
Filebrowser 一键安装脚本

bash <(curl -s -L https://raw.githubusercontent.com/66yellow/filebrowser/master/filebrowser.sh)

生成自签证书
从头开始创建一个 2048 位的私钥（domain.key）和一个自签证书（domain.crt）：

openssl req -newkey rsa:2048 -nodes -keyout domain.key -x509 -days 365 -out domain.crt

其中选项-x509告诉req子命令创建一个自签名的证书。-days 365 选项指定证书的有效期为365天。继续回答 CSR 信息提问，完成该过程。

acme.sh --install-cert -d abc.com --ecc \
--cert-file      /etc/filebrowser/crt.crt  \
--key-file       /etc/filebrowser/key.key

# RPC 服务 SSL/TLS 加密, 默认：false
# 启用加密后必须使用 https 或者 wss 协议连接
# 不推荐开启，建议使用 web server 反向代理，比如 Nginx、Caddy ，灵活性更强。
#rpc-secure=false

# 在 RPC 服务中启用 SSL/TLS 加密时的证书文件(.pem/.crt)
#rpc-certificate=/root/.aria2/xxx.pem

# 在 RPC 服务中启用 SSL/TLS 加密时的私钥文件(.key)
#rpc-private-key=/root/.aria2/xxx.key
