# MEMORANDUM

## git clone soooooooso slow

``` txt
151.101.72.249 github.global.ssl.fastly.net
192.30.253.112 github.com
```

> Refresh the hosts

``` txt
ipconfig /flushdns     \#清除DNS缓存内容。
ipconfig /displaydns    //显示DNS缓存内容
```

Test,  worked!

## docker configuration

使用vi修改 /etc/docker/daemon.json 文件并添加上"registry-mirrors": \["

[https://registry.docker-cn.com](https://registry.docker-cn.com/)

"\]，如下：

``` txt
vi /etc/docker/daemon.json
{
"registry-mirrors": \['[https://registry.docker-cn.com](https://registry.docker-cn.com/)'\]
}
```

## how to use markdown

[github markdown handbook](https://guides.github.com/features/mastering-markdown/)

## personal time manangement

### Year \*\*\*\* / \*\* Week \(for example 2018 / 20 week\)

| Day | Time | Duration | Subject | Remark | Feedback |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Monday | \*\* min | time - time | what subject | - | DONE |
| Tuesday | \*\* min | time - time | what subject | - | NO |
| Wednesday | \*\* min | time - time | what subject | anything else | DOEN |
| Thursday | \*\* min | time - time | what subject | anything else | NO |
| Friday | \*\* min | time - time | what subject | anything else | NO |

#### Task

1. Find a way to slove the prblem..

> * what is the problem
> * divide the problem into serveral parts which i can do that in serveral hours

1. Solve the problem

> * solve the first step of the problem
> * solve the second stop of the problem
> * ...

```
 ....

n. other works
```

#### Divide the problem into smallest parts which i can solve it in serveral hours or minutes