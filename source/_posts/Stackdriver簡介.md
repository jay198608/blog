---
title: Stackdriver介紹
date: 2018-07-27 21:55:07
tags:
---
## Stackdriver功能介紹
針對雲端應用程式而打造，可監控、記錄與診斷雲端應用程式的健康狀態、效能和可用性，更快速地找出問題並加以修復，除了監控GCP，也可以加入監控AWS。
## 定價
Stackdriver 提供基本級和進階級。進階級採統一費率，每項應收費的監控資源每月 $8.00 美元，未達 1 個月則按照使用小時比例計算。
![](/img/fee.png)

自 2018 年 6 月 30 日起，Stackdriver 將改為按用量計費制，計價費率是依使用者的使用量和費用計算，用多少就付多少。Stackdriver有提供Monitoring與Logging的
[免費配額](https://cloud.google.com/stackdriver/pricing_v2)：

**Monitoring**
可清楚監控雲端應用程式的效能、運作時間與整體健康狀態，蒐集GCP VM裡背景運作的服務到GCP來監控。
若安裝 **monitoring agent** 可以訪問額外的系統資源和應用服務以及[Third-party Applications](https://cloud.google.com/monitoring/agent/plugins/)，即使不安裝 **monitoring agent**，也可以監控disk、cpu、network、process…等資源。
![](/img/fee-monitoring.png)

**Logging**
儲存、搜尋、分析、監控 GCP 與 AWS 的記錄資料與事件，可即時分析所有記錄資料。若安裝 **logging agent** 可以蒐集第三方應用程式和系統應用程式的log，預設的[logs清單](https://cloud.google.com/logging/docs/agent/default-logs)。
![](/img/fee-logging.png)



## 建立 Stackdriver 帳號
開始監控前須先建立Stackdriver帳號
![](/img/Account-1.png)
![](/img/Account-2.png)


#### 安裝 monitoring agent 與 logging agent
**Windows 下載連結**
[Monitoring aggent](https://repo.stackdriver.com/windows/StackdriverMonitoring-GCM-46.exe)
[Logging agent](https://dl.google.com/cloudagents/windows/StackdriverLogging-v1-8.exe)


#### Linux指令
```
# To install the Stackdriver monitoring agent:
$ curl -sSO https://dl.google.com/cloudagents/install-monitoring-agent.sh
$ sudo bash install-monitoring-agent.sh
# To install the Stackdriver logging agent:
$ curl -sSO https://dl.google.com/cloudagents/install-logging-agent.sh
$ sudo bash install-logging-agent.sh
```
