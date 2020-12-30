# Proxys
根据zu1k/proxypool自动抓取tg频道、订阅地址、公开互联网上的ss、ssr、vmess、trojan节点信息，聚合去重后提供节点列表，每15分钟更新



1.下载golang安装包

wget https://golang.org/dl/go1.15.6.linux-amd64.tar.gz

2.解压至/usr/local文件夹

tar -C /usr/local -xzf go1.15.6.linux-amd64.tar.gz

3.配置环境变量 vim /etc/profile

Insert在尾部黏贴以下内容

export GOROOT=/usr/local/go #设置为go安装的路径

export GOPATH=$HOME/go #默认安装包的路径

export PATH=$PATH:$GOROOT/bin:$GOPATH/bin

export PORT=80

Esc :wq退出

source /etc/profile  使修改生效.

(需安装git命令  yum install git)
克隆代码

git clone -b master https://github.com/Sansui233/proxypool.git

进入目录

cd proxypool

创建项目

go build

首次配置时间上比较长

完成后进入目录

cd proxypool

修正config文件夹中的config.yaml和source.yaml
配置文件请参考wiki
https://github.com/Sansui233/proxypool/wiki/%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E

保存配置后运行

nohup ./proxypool -c config/config.yaml >/dev/null 2>&1

就可以访问你的网站了

