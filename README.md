# gitbook

This book is used to show my thoughts about coder experience

## **git clone soooooooso slow, here is the soultion:**

> 151.101.72.249 github.global.ssl.fastly.net
>
> 192.30.253.112 github.com

Refresh the hosts

> ipconfig /flushdns     \#清除DNS缓存内容。
>
> ipconfig /displaydns    //显示DNS缓存内容

Test,  worked!



## docker configuration

使用vi修改 /etc/docker/daemon.json 文件并添加上”registry-mirrors”: \[“

[https://registry.docker-cn.com](https://registry.docker-cn.com/)

“\]，如下：

> vi /etc/docker/daemon.json
>
> {
>
> “registry-mirrors”: \[‘[https://registry.docker-cn.com](https://registry.docker-cn.com/)’\]
>
> }





