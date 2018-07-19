---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 特性概觀

IBM Cloud Direct Link 供應項目提供從外部來源到客戶 IBM Cloud 專用網路的連線功能。Direct Link 可以視為傳統網站對網站之 VPN 解決方案的替代方案，其設計適合在遠端網路與其 IBM Cloud 環境之間需要更一致、更高傳輸量連線功能的客戶。有四種連線類型可用：
 
 * **IBM Cloud Direct Link Exchange** 讓客戶能利用 Exchange 提供者，提供對其 IBM Cloud 的連線功能。Exchange 提供者是已經使用多方承租戶高傳輸量鏈結連上 IBM Cloud 網路的通訊業者或網路提供者。客戶通常能向此提供者購買虛擬電路，得到成本較低的連線功能，因為從 {{site.data.keyword.BluSoftlayer_notm}} 到 Exchange 提供者的實體連線功能已經就緒，並與其他客戶共用。
 
 * **IBM Cloud Direct Link Connect** 讓客戶能利用透過我們合作夥伴的連線，這些合作夥伴擁有且營運了以設施為基礎的網路。使用 IBM Cloud Direct Link Connect，IBM 和合作夥伴會透過雙重的第 2 層 10G NNI，以第 2 層和第 3 層連接客戶。
 
 * **IBM Cloud Direct Link Dedicated** 讓客戶將專用、單一模式的光纖交叉連接連入到他們自己的 IBM Cloud 專用網路。
 
 * **IBM Cloud Direct Link Dedicated Hosting** 提供與 IBM Cloud Direct Link Dedicated 類似的連線功能，但連線點與 {{site.data.keyword.BluSoftlayer_notm}} 資料中心相鄰，這樣可改善較高效能使用案例的延遲。IBM Cloud 以此解決方案提供各種可自訂的主機託管服務。
  
IBM Cloud Direct Link 服務是經過遞送的 OSI 第 3 層服務。它提供對 {{site.data.keyword.BluSoftlayer_notm}} 專用網路骨幹的直接連線，具有低延遲，且速度最高可達 10Gbps。由於提高了建立此第 3 層連線功能的彈性，IBM Cloud Direct Link 讓客戶能利用：
 * 遠端主機的雙重 IP
 * NAT
 * BYOIP 的通道作業
