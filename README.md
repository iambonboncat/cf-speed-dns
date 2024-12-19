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

## 2024年12月20日，由于Github不支持python不支持3.7版本，导致更新CF域名IP失败，修改dns_cf.yml文件，以使用python 3.12版本。

## 摸索出来的使用方法
*
* 必要条件：拥有CF账号和在CF上解释的域名
* 
* 一、Fork项目到自己的github仓库repositories
* 
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
* 三、登入CF获取API token和Zone ID，并新建一个自动更新最优ip地址的二级域名。
  * 点击需要自动更新ip的域名，把区域ID复制下来备用，这个就是CF_ZONE_ID，
  * ![image](https://github.com/user-attachments/assets/5ecffa5a-fbd2-4e42-88f1-48b52f17d52a)
  * 点击 获取你的API令牌，
  * ![image](https://github.com/user-attachments/assets/ac18440e-e2db-4615-8f44-eef007656872)
  * 点击 创建令牌，
  * ![image](https://github.com/user-attachments/assets/be1d4f08-1f71-4e55-a34c-af6ccf8e2240)
  * 选择 编辑区域DNS使用模板，
  * ![image](https://github.com/user-attachments/assets/b2e505fe-ce0d-4d5e-8b8f-9f4ff522bbcf)
  * 选择 需要自动更新IP的域名，
  * ![image](https://github.com/user-attachments/assets/debddf43-bacd-4696-99b5-d789a5908a6c)
  * 点击 继续以显示摘要，
  * ![image](https://github.com/user-attachments/assets/4d7e5ac5-c9d8-4990-be49-a63d82eb4ef5)
  * 点击 创建令牌，
  * ![image](https://github.com/user-attachments/assets/b73574c2-7dad-4623-8028-c6cc6c771e50)
  * 复制 创建好的令牌备用，
  * ![image](https://github.com/user-attachments/assets/7ffb24ec-2192-4293-86a1-c67a7fcaa4ac)
  * 顺便在DNS项目里面新建一个二级域名，类型A，名称dns，ip地址随便填一个备用。
* 四、设置Actions的配置
  * 在setting页面，点击secrets and variables下面的actions
  * ![image](https://github.com/user-attachments/assets/02a27c4b-293c-4595-a04d-b9288a607bb3)
  * 点击下方的新建
  * ![image](https://github.com/user-attachments/assets/0233ae39-003f-43ec-bf23-ed8ccaf2ddc6)
  * 填入Name和Secret
  * ![image](https://github.com/user-attachments/assets/45c8b71b-0da3-4a0b-97de-719ad5f63bb2)
  * 分别新建三个secrets，CF_API_TOKEN对应填入API令牌，CF_ZONE_ID填入区域ID，CF_DNS_NAME填入你需要自动更新的二级域名（例如dns.XXXXX.xyz）
  * ![image](https://github.com/user-attachments/assets/fac365f2-48e7-4d40-b245-3f52ab9b4945)
* 五、到此处，已经把需要设置填写的地方都部署设置好了，接下来就是启动Actions。
* 点击Actions，进入界面，把几个需要启动workflow的文件打开。
* ![image](https://github.com/user-attachments/assets/311c37a1-83e6-476e-8b62-c3517ceb23c3)
* 接下来就等这自动部署和更新。如果你要手动更新，也可以点击run workflow。
* ![image](https://github.com/user-attachments/assets/c13bae55-4bd5-47f0-b77c-5b768936dd95)
* 如果一切顺利，你就会发现，之前乱填的DNS二级域名ip更新成了最快的那一个ip！












