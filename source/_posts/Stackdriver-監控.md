---
title: Stackdriver 監控
date: 2018-08-06 17:00:23
tags:
---
## 一、建立 Stackdriver 帳號
開始監控前須先建立Stackdriver帳號
![](/img/Account-1.png)
![](/img/Account-2.png)

**Monitoring Overview**
![](/img/Monitoring_Overview.png)

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

## 二、Resources - Metrics Explorer
**Metric設定**
Resource types：監控的資源
Select a metric：選擇監控該資源的指標
![](/img/UptimeCheck_Dashboard.png)

**View Options**
依喜好調整圖表的模式、參考值、歷史資料…等設定。
![](/img/Resources_Metrics Explorer_Viewoptions.png)

**調整線圖模型**
![](/img/Resources_Metrics Explorer_Line.png)

## 三、建立Group
![](/img/Group.png)

## 四、Uptime Check
透過從世界各地來驗證服務的可用性，經過的地區有維吉尼亞州、奧勒岡州、愛荷華州、比利時、新加坡、聖保羅，每個Stackdriver帳戶最多可建立100個Uptime Checks，第一次建立需等候一段時間。以下以驗證HTTP來作示範。
![](/img/UptimeCheck_Dashboard.png)

1. 建立VM（Linux）並允許http、https流量

2. 安裝 Apache2 HTTP Server
```
sudo apt-get update
sudo apt-get install apache2 php7.0
sudo service apache2 restart
```

3. 測試Apache服務是否起來：「http://[外部IP]」
![](/img/Apache.png)

4. 建立Uptime Check，Check Type選擇HTTP，監控範圍選擇Group後可先Test看是否可運作。
![](/img/Uptimecheck.png)



## 五、新增告警
![](/img/Alert_Set.png)
**Conditions**：設定監控instance、LB...等條件
**Notifications**：告警通知可選擇Email、簡訊、Slack…等通知方式
**Documentation**：設定當觸發告警時，發送email時的訊息內容
**Name this policy**：命名該告警政策名稱


**告警mail**
![](/img/Alert_mail.png)


## 六、建立Dashboards
進入Dashboard點選「ADD CHART」，在METRIC選擇「Resoruce type」與「Metric」並save即完成一張圖表。
![](/img/dashboard.png)

**變更Dashboard名稱**
![](/img/dashboard-2.png)

**查看圖表**
![](/img/dashboard-1.png)

**公開分享圖表**
分享的圖表URL可直接分享給其他人
![](/img/dashboard-share.png)

**View Log**
![](/img/dashboard-log.png)

**Public Charts**
可查看公開分享的圖表資料，也可點 Unshare 取消分享。
![](/img/PublicCharts.png)