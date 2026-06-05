<div align="center">

# YR4399

**微信小程序自动化 · Docker 签到矩阵 · 任务引擎**

</div>

---

### 脚本功能列表

| 脚本名称 | 类型 | 当前状态 |
| :--- | :----: | :----: |
| 铛铛一下签到+抽奖+提现 | 微信小程序 | ✅ |
| 嘉立创金豆商城签到 | 微信小程序 | ✅ |
| 倍轻松签到+发帖+评论+浏览商城 | 微信小程序 | ✅ |
| 七彩虹签到 | 微信小程序 | ✅ |
| 茶白道签到 | 微信小程序 | ✅ |
| 三福签到 | 微信小程序 | ✅ |
| DT生活签到 | 微信小程序 | ✅ |
| 优智云家签到 | 微信小程序 | ✅ |
| 奈雪点单签到 | 微信小程序 | ✅ |
| 飞蚂蚁旧衣回收签到+步数兑换 | 微信小程序 | ✅ |
| 君品荟签到+花园 | 微信小程序 | ⚠️ |
| 海天美味馆签到 | 微信付费小程序 | ✅ |
| 国乐酱酒签到 | 微信付费小程序 | ✅ |
| iQOO社区签到 | 微信付费小程序 | ✅ |
| 爱玛签到 | 微信付费小程序 | ✅ |
| 小紫有约签到 | 微信付费小程序 | ✅ |
| 泰康在线保险签到+答题+浏览 | 微信小程序 | ✅ |
| 恩山论坛签到 | APP | ✅ |
| 智谱AI签到 | APP | ✅ |

---

### 微信小程序脚本

需要配置 `wx_server_url` / `wx_auth` 通过 WCS 获取微信小程序 `code`。

| 脚本名称 | 说明 | 当前状态 |
| :--- | :---- | :----: |
| BREO.py | 倍轻松 签到+发帖+评论+浏览商城 | ✅ |
| jph_runner.py | 君品荟 签到+花园（花园写操作需WCS暴露session_key） | ⚠️ |
| 三福.py | 三福 签到 | ✅ |
| dt生活签到.py | DT生活 签到 | ✅ |
| 优智云家.py | 优智云家 签到 | ✅ |
| 奈雪的茶.py | 奈雪点单 签到 | ✅ |
| 铛铛一下.py | 铛铛一下旧衣服回收 签到+抽奖+提现 | ✅ |
| 泰康在线保险.py | 泰康在线保险 签到+兑换红包+答题+浏览推荐 | ✅ |
| dd1x_sign.js | 铛铛一下 签到+抽奖 | ✅ |
| jlc_sign.js | 嘉立创金豆商城 签到 | ✅ |
| colorful.js | 七彩虹 签到 | ✅ |
| cbd_sign.js | 茶白道 签到 | ✅ |
| 飞蚂蚁旧衣回收.js | 飞蚂蚁 签到+步数兑换 | ✅ |
| haitian.js | 海天美味馆（付费code） | ✅ |
| gyjj.js | 国乐酱酒（付费code） | ✅ |
| iqoo.js | iQOO社区（付费code） | ✅ |
| aima.js | 爱玛（付费code） | ✅ |

---

### 已适配小程序 AppID

| 小程序 | AppID | 备注 |
| :--- | :--- | :--- |
| 铛铛一下 | `wxe378d2d7636c180e` | 签到+抽奖+提现 |
| 嘉立创金豆商城 | `wx6c7b851c877dba42` | CAS静默登录 |
| 海天美味馆 | `wx7a890ea13f50d7b6` | 需要手机号授权的付费code |
| 倍轻松 | `wx61457400e4212cec` | 签到+发帖+评论+浏览商城 |
| 君品荟 | `wx8d41cdc44c8aeaab` | 商城签到✅，花园部分可用 |
| 七彩虹 | `wx49018277e65fc3e1` | 需手机号授权 |
| 茶白道 | `wx2804355dbf8d15c3` | 需两次登录 |
| 优智云家 | `wxa61f98248d20178b` | 微盟平台 |
| 三福 | `wxfe13a2a5df88b058` | |
| 奈雪的茶 | `wxab7430e6e8b9a4ab` | |
| 飞蚂蚁旧衣回收 | `wx501990400906c9ff` | 步数兑换 |
| 泰康在线保险 | `wx9e3e7020c4a10356` | unionid登录 |

---

### 部署架构

```
┌─────────────────────────────────────────────┐
│  Docker Compose                              │
│                                              │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │  daidai   │  │ wechat-  │  │  qinglong│  │
│  │  panel    │  │ server   │  │  (青龙)   │  │
│  │ :8088     │  │ :8787    │  │ :5700    │  │
│  └─────┬─────┘  └─────┬────┘  └──────────┘  │
│        │              │                       │
│        └──── WCS ─────┘                       │
│         /wx/code  /wx/operatedata             │
│         /wx/encryptkey                        │
└─────────────────────────────────────────────┘
```

---

### 青龙面板拉库命令

```
ql repo https://github.com/YR4399/wx-mini-scripts.git backup main
```

---

### Tech Stack

![Python](https://img.shields.io/badge/Python-主力语言-3776AB?style=flat-square&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-容器化-2496ED?style=flat-square&logo=docker&logoColor=white)
![WeChat](https://img.shields.io/badge/WeChat-小程序-07C160?style=flat-square&logo=wechat&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-运维-FCC624?style=flat-square&logo=linux&logoColor=black)

---

### GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=YR4399&show_icons=true&theme=tokyonight&hide_border=true" width="48%" />
<img src="https://github-readme-streak-stats.herokuapp.com/?user=YR4399&theme=tokyonight&hide_border=true" width="48%" />

</div>

---

### Star History

<a href="https://www.star-history.com/#YR4399/wx-mini-scripts&type=date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=YR4399/wx-mini-scripts&type=date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=YR4399/wx-mini-scripts&type=date" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=YR4399/wx-mini-scripts&type=date" />
 </picture>
</a>

---

<div align="center">

**自动签到 · 任务引擎 · Docker 一键部署**

</div>
