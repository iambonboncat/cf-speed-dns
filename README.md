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
* 必要条件：拥有CF账号和在CF上解释的域名
* 一、Fork项目到自己的github仓库repositories
* 二、部署这个项目到github pages
*  进入这个，点击上面的setting。
*  ![image](https://github.com/user-attachments/assets/3288c27b-be62-4122-ae25-ecf4d0a67b09)
*  点击左侧pages。
* ![image](https://github.com/user-attachments/assets/9153bba2-6df5-425a-aa0d-83c56ca432ac)
*  选择一下Build and deployment 的源 Source。
* ![image](https://github.com/user-attachments/assets/0c3a2fd9-391a-4cb9-8d94-a1a1dbbd04e5)
*  如果你在CF上有自己的域名，可以在下面这个框框上填上，以绑定xxx.github.io/cf-speed-dns这个域名跳转。
* ![image](https://github.com/user-attachments/assets/6da71fee-8b53-427c-9fe2-13bc1971a06a)
*  同时在你的CF的域名下，添加一个cname的二级域名指向xxx.github.io。
* ![image](https://github.com/user-attachments/assets/325e7f88-c217-4651-a511-e79e4820b710)
*  如果绑定成功，在github这个页面，会出现DNS check successful字样。
* ![image](https://github.com/user-attachments/assets/3354ef1c-0152-48be-86db-fd9b897a5c66)
*  这时候，你就能用刚才添加的域名直接访问网页。
* 三、设置Actions的配置
* 






