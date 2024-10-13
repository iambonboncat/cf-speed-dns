## cf-speed-dns是什么?
CloudflareSpeedTest 推送「每5分钟自选优选 IP」获取Cloudflare CDN 延迟和速度最快 IP ！

## cf-speed-dns有哪些功能？
* CloudflareSpeedTest优选IP，实时更新列表页面。[https://ip.164746.xyz](https://ip.164746.xyz)
* CloudflareSpeedTest优选IP，Top接口(默认)[https://ip.164746.xyz/ipTop.html](https://ip.164746.xyz/ipTop.html)；Top10接口[https://ip.164746.xyz/ipTop10.html](https://ip.164746.xyz/ipTop10.html)。
* DNSPOD实时域名解析推送，fork 本项目。
  * Action配置，Actions secrets and variables 添加 DOMAIN(例如：164746.xyz)，SUB_DOMAIN（例如：dns），SECRETID（xxxxx），SECRETKEY（xxxxx），PUSHPLUS_TOKEN（xxxxx）。
* DNSCF实时域名解析推送，fork 本项目。
  * Action配置，Actions secrets and variables 添加 CF_API_TOKEN(例如：xxxxx)，CF_ZONE_ID（例如：xxxxx），CF_DNS_NAME（dns.164746.xyz），PUSHPLUS_TOKEN（xxxxx）。
* 接入PUSHPLUS消息通知。[https://www.pushplus.plus/push1.html](https://www.pushplus.plus/push1.html)

## 接口请求
```javascript
curl 'https://ip.164746.xyz/ipTop.html'
```
## 接口返回
```javascript
104.16.204.6,104.18.103.125
```

## 感谢
[XIU2](https://github.com/XIU2/CloudflareSpeedTest)、[ddgth](https://github.com/ddgth/cf2dns)

## 摸索出来的使用方法
必要条件：拥有CF账号
一、Fork项目到自己的github仓库repositories
二、部署这个项目到github pages
 进入这个，点击上面的setting![image](https://github.com/user-attachments/assets/3288c27b-be62-4122-ae25-ecf4d0a67b09)
 点击左侧pages![image](https://github.com/user-attachments/assets/9153bba2-6df5-425a-aa0d-83c56ca432ac)

