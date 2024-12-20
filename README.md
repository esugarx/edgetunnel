# edgetunnel
本项目基于 CM 的脚本

## 变量说明

| 变量名 | 示例 | 必填 | 备注 |
|--------|---------|-|-----|
| UUID | 673d64d5-0802-4d3f-acd0-71084edcddf0 |√| 唯一标示 |
| PROXYIP | proxyip.fxxk.dedyn.io |×| 作为访问CFCDN站点的代理节点(支持多ProxyIP, ProxyIP之间使用`,`或 换行 作间隔) |
| SOCKS5  | user:password@127.0.0.1:1080 |×| 优先作为访问CFCDN站点的SOCKS5代理 |
| ADD | icook.tw:2053#官方优选域名 |×| 本地优选TLS域名/优选IP(支持多元素之间`,`或 换行 作间隔) |
| ADDAPI | [https://raw.github.../addressesapi.txt](https://raw.githubusercontent.com/cmliu/WorkerVless2sub/main/addressesapi.txt) |×| 不解释, 懂得都懂 |
| ADDNOTLS | icook.hk:8080#官方优选域名 |×| 本地优选noTLS域名/优选IP(支持多元素之间`,`或 换行 作间隔) |
| ADDNOTLSAPI | [https://raw.github.../addressesapi.txt](https://raw.githubusercontent.com/cmliu/CFcdnVmess2sub/main/addressesapi.txt) |×| 不解释, 懂得都懂 |
| ADDCSV | [https://raw.github.../addressescsv.csv](https://raw.githubusercontent.com/cmliu/WorkerVless2sub/main/addressescsv.csv) |×| 不解释, 懂得都懂 |
| DLS | 8 |×| 不解释, 懂得都懂 |
| TGTOKEN | 6894123456:XXXXXXXXXX0qExVsBPUhHDAbXXX |×| 发送TG通知的机器人token |
| TGID | 6946912345 |×| 接收TG通知的账户数字ID |
| SUB | VLESS.fxxk.dedyn.io | × | 内建域名、IP节点信息的订阅生成器地址 |
| SUBAPI | api.v1.mk |×| clash、singbox等 订阅转换后端 |
| SUBCONFIG | [https://raw.github.../ACL4SSR_Online_Full_MultiMode.ini](https://raw.githubusercontent.com/cmliu/ACL4SSR/main/Clash/config/ACL4SSR_Online_Full_MultiMode.ini) |×| clash、singbox等 订阅转换配置文件 |
| RPROXYIP | false |×| 设为 true 即可强制获取订阅器分配的ProxyIP(需订阅器支持)|
| URL302 | https://t.me/CMLiussss |×| 主页302跳转(支持多url, url之间使用`,`或 换行 作间隔, 小白别用) |
| URL | https://t.me/CMLiussss |×| 主页伪装(支持多url, url之间使用`,`或 换行 作间隔, 乱设容易触发反诈) |
| CFEMAIL | admin@gmail.com |×| CF账户邮箱(与`CFKEY`都填上后, 订阅信息将显示请求使用量, 小白别用) |
| CFKEY | c6a944b5c956b6c18c2352880952bced8b85e |×| CF账户Global API Key(与`CFEMAIL`都填上后, 订阅信息将显示请求使用量, 小白别用) |

**注意: 填入`SOCKS5`后将不再启用`PROXYIP`！请二选一使用！！！**

**注意: 填入`SUB`后将不再启用`ADD*`类变量生成的订阅内容！请二选一使用！！！**

**注意: 同时填入`CFEMAIL`和`CFKEY`才会启用显示请求使用量，但是不推荐使用！没必要给一个Worker项目这么高的权限！后果自负！！！**

## 实用技巧

**该项目部署的节点可通过节点PATH(路径)的方式，使用指定的`PROXYIP`或`SOCKS5`!!!**

- 指定 `PROXYIP` 案例
   ```url
   /proxyip=proxyip.fxxk.dedyn.io
   /?proxyip=proxyip.fxxk.dedyn.io
   /proxyip.fxxk.dedyn.io (仅限于域名开头为'proxyip.'的域名)
   ```

- 指定 `SOCKS5` 案例
   ```url
   /socks5=user:password@127.0.0.1:1080
   /?socks5=user:password@127.0.0.1:1080
   /socks://dXNlcjpwYXNzd29yZA==@127.0.0.1:1080
   /socks5://user:password@127.0.0.1:1080
   ```

## 免责声明

本免责声明适用于 GitHub 上的 “edgetunnel” 项目（以下简称“该项目”），项目链接为：https://github.com/esugarx/edgetunnel

### 用途

该项目被设计和开发仅供学习、研究和安全测试目的。它旨在为安全研究者、学术界人士和技术爱好者提供一个了解和实践网络通信技术的工具。

### 合法性

使用者在下载和使用该项目时，必须遵守当地法律和规定。使用者有责任确保他们的行为符合其所在地区的法律、规章以及其他适用的规定。

### 免责

1. 作为该项目的作者，我（以下简称“作者”）强调该项目应仅用于合法、道德和教育目的。
2. 作者不鼓励、不支持也不促进任何形式的非法使用该项目。如果发现该项目被用于非法或不道德的活动，作者将强烈谴责这种行为。
3. 作者对任何人或团体使用该项目进行的任何非法活动不承担责任。使用者使用该项目时产生的任何后果由使用者本人承担。
4. 作者不对使用该项目可能引起的任何直接或间接损害负责。
5. 通过使用该项目，使用者表示理解并同意本免责声明的所有条款。如果使用者不同意这些条款，应立即停止使用该项目。

作者保留随时更新本免责声明的权利，且不另行通知。最新的免责声明版本将会在该项目的 GitHub 页面上发布。

## 风险提示

- 通过提交虚假的节点配置给订阅服务，避免节点配置信息泄露。
- 另外，您也可以选择自行部署 [WorkerVless2sub 订阅生成服务](https://github.com/cmliu/WorkerVless2sub)，这样既可以利用订阅生成器的便利。

# 感谢

[zizifn](https://github.com/zizifn/edgetunnel)、[3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)、[Stanley-baby](https://github.com/Stanley-baby)、[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)、[SHIJS1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)、[肥羊订阅转换](https://suburl.v1.mk)
