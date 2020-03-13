## 用于在 goorm上运行v2ray 
```shell
wget https://raw.githubusercontent.com/byxiaopeng/goorm-v2ray/master/goormv2.sh

chmod +x goormv2.sh

./goormv2.sh
```
## 后台运行v2ray

```shell
nohup /v2ray/v2ray -config=/v2ray/config.json >out.txt 2>&1 &
```
## 配置
goorm上的Run URL & Port +Add 添加 Port 8088 
## 客户端连接
域名为
goorm的Run URL & Port的URL
端口为 443

"id": "aa12098f-56f3-49ed-bd5d-267f3ce2e873"

alterId": 64

"network": "ws"

path:/

tls

##cloudflare workers 反代
workers 添加
```shell
addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="goorm的Run URL & Port的URL";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)
```
地址改为workers分配的地址 
