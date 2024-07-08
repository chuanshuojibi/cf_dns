# fork自https://github.com/ZhiXuanWang/cf-speed-dns项目
由于未知原因，我直接fork的项目一直运行失败，所以我本地实际加了参数结果能跑，于是试了半天还是没把项目改成功，所以另起了一个发现成功运行了。
## 项目介绍
#### 项目功能：
自动推送https://ip.164746.xyz 中优选出的ip到cloudflare
#### 配置方法
1. fork本项目
2. 进入fork的项目复然后制https://github.com/chuanshuojibi/cf_dns/blob/main/%E5%B7%A5%E4%BD%9C%E6%B5%81%E4%BB%A3%E7%A0%81 中的工作流代码
   打开上方的action，新建一个工作流，将代码粘贴进去。
3. 打开项目的settings，Actions secrets and variables，action  ，new  Repository secrets 逐个添加以下的内容
4. 添加 CF_API_TOKEN(进入cf后在概述，点击获取您的api令牌，创建令牌得到的才是)，CF_ZONE_ID（概述里那个区域id就是），CF_DNS_NAME（dns.164746.xyz），PUSHPLUS_TOKEN（PUSHPLUS消息通知。https://www.pushplus.plus/push1.html）。
#### 测试运行
返回action，左侧应该有一个叫push_cf的或者其他，点击之后右边会有run workflow，然后看看没报错就正常了，有报错就问ai。

#### 时间设定，
在项目中的.github/workflows中有个main.yml,其中有个正则表达式![image](https://github.com/chuanshuojibi/cf_dns/assets/106017459/761d392b-f8ee-4005-81b3-a8635ead234b)
发给ai让他修改，默认的是8小时执行一次。
