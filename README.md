# 【零基础】X-UI面板，搭建vless+vision+reality节点
简体中文

> 声明：该项目仅供个人学习、交流，请遵守当地法律法规,勿用于非法用途;请勿用于生产环境  

支持单端口多用户、多协议的 xray 面板，究极缝合怪     
欢迎大家使用并反馈意见或提交Pr,帮助项目更好的改善  
如果您觉得本项目对您有所帮助,不妨给个star:star2:支持我  
或者你恰巧有购买服务器的需求,可以通过文末的赞助部分支持我~ 

# 文档目录  
- [功能介绍](#功能介绍)
- [一键安装](#一键安装)  

# X-UI功能介绍

- 系统状态监控
- 支持单端口多用户、多协议，网页可视化操作
- 支持的协议：vmess、vless、trojan、shadowsocks、shadowsocks 2022、dokodemo-door、socks、http
- 支持配置更多传输配置：http、tcp、ws、grpc、kcp、quic
- 流量统计，限制流量，限制到期时间，一键重置与设备监控
- 可自定义 xray 配置模板
- 支持 https 访问面板（自备域名 + ssl 证书）
- 支持一键SSL证书申请且自动续签
- Telegram bot通知、控制功能
- 更多高级配置项，详见面板 

# 建议系统
CentOS 7+
Ubuntu 16+
Debian 8+

# 一键安装
在安装前请确保你的系统支持`bash`环境,且系统网络正常  

&#x26A1;从原版升级也可使用该命令，数据不会丢失&#x26A1;

```
echo -e "net.ipv6.conf.all.disable_ipv6=1\nnet.ipv6.conf.default.disable_ipv6=1\nnet.ipv6.conf.lo.disable_ipv6=1" >> /etc/sysctl.conf
sysctl -p
apt update -y
apt install -y curl
apt install -y socat
bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/master/install.sh)
```
# 问题汇总
1.PING延迟太高，检查nameserve并修改如下
```
nano /etc/resolv.conf
nameserver 8.8.8.8
nameserver 1.1.1.1
```
2.放行端口
```
iptables -I INPUT -p tcp --dport 3600 -j ACCEPT
```
