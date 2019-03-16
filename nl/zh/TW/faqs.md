---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# 常見問題 (FAQ)
{: #faqs}

本節包含關於 {{site.data.keyword.cloud}} Direct Link 的部分常見問題的回答。 

## IBM Cloud Direct Link 如何運作？
{:faq}

對於每位 Direct Link 客戶，IBM Cloud 團隊會指派小型的專用子網路來建置 {{site.data.keyword.BluSoftlayer_notm}} 交叉連接路由器 (XCR) 與客戶的邊緣路由器 (CER)
之間的點對點網路。然後，{{site.data.keyword.BluSoftlayer_notm}} 與客戶會配置 BGP，以便在環境之間交換路徑。最後，{{site.data.keyword.BluSoftlayer_notm}} 會讓客戶進入 VRF，以允許實作對客戶遠端網路專用位址空間的非唯一路徑。

## IBM Cloud 會計量 Direct Link 產品的頻寬嗎？
{:faq}

是的。透過「客戶」與 IBM Cloud 之間的 Direct Link 服務所產生的頻寬使用免費且無計量，而從 IBM Cloud 服務到公用網際網路的出埠頻寬，IBM Cloud 會計量。

## Direct Link 的計費何時開始？
{:faq}

Direct Link Connect 的費用涵蓋 IBM Cloud 基礎架構上的服務終止的成本。 

「基礎架構服務」會事先計費，並從接受客戶的訂單之後開始；不過，由於 IBM Cloud Direct Link 的本質，Direct Link 服務計費將在建立與 IBM Cloud 的「邊界閘道通訊協定 (BGP)」階段作業時開始，或在提供服務金鑰給客戶之後 30 天開始。 

計費會在下列情況之後停止 (1) 客戶要求刪除電路，且 (2)「Connect 提供者」或「網路服務提供者」已取消佈建電路。

## Direct Link 的其他方是否會產生額外費用？
{:faq}

您可能會有來自 Exchange 提供者或網路服務提供者的其他費用。費用資訊請洽詢您的提供者。

## 如何使用 IBM Cloud Direct Link 來達到備援？
{:faq}

Direct Link 不提供固有的備援服務。Direct Link 可以提供「多樣化」連線，讓客戶能夠透過 BGP 來建立備援。若要透過 Direct Link 達到多樣性，您可以連接至多個 IBM Cloud Direct Link Dedicated 提供者或 {{site.data.keyword.BluSoftlayer_notm}} 的 Exchange 提供者。或者，透過 Exchange 與 Connect，您可以運用多樣化 NNI 來搭配 IBM Cloud Direct Link 提供者。

##  Direct Link 的預設「本端」遞送與廣域遞送附加程式之間有什麼差異？
{:faq}

使用我們的標準 Direct Link 供應項目，您可以在選取的地區的資料中心之間傳送資料流量。如果需要存取指定地區之外的其他資料中心，必須訂購廣域遞送附加程式。這個模型是根據在您訂購 Direct Link 連線時生效的 ACL（存取控制清單）。 

## Direct Link 廣域遞送附加程式的出埠頻寬超額如何計費？
{:faq}

當您超出頻寬配給時，超額會依月份計費，但這只會針對出埠頻寬。入埠頻寬免費，且不予計量。出埠頻寬的計費是根據您的資料跨越之兩個地區中較高的費率。例如，如果您的 Direct Link 配置在 DAL03，而資料流量通過了墨西哥，您會被依墨西哥的頻寬費率計費。

## 為何有 Direct Link 廣域遞送附加程式套件存在？
{:faq}

我們已新增廣域遞送附加程式，避免客戶在資料中心地區之外遍訪時遭遇非預期的資料成本。它可讓大部份的客戶成本降低，也讓能全球上線的客戶能夠輕鬆地聯繫全球所有地區。不過，通常客戶只需要本端頻寬套件。

## 如果我連接至某地區（例如達拉斯）中的 Direct Link Dedicated、Direct Link Connect 或 Direct Link Cloud Exchange，我能透過 Direct Link 存取美國的其他地區嗎？
{:faq}

是的，如果您選擇「廣域遞送」附加程式，便可以存取地區之外的區域。如果未選取這個選項，則您的 Direct Link 資料流量將侷限在您所選 PoP 的地區。如需詳細資料，請參閱[定價文件](/docs/infrastructure/direct-link/pricing.html)。

## 我可以從給定的 Direct Link 位置連接至任何可用的地區嗎？
{:faq}

是的，只要您訂購 Direct Link 時選取了「廣域遞送」附加程式。

## 我可以限制我的 Direct Link 能聯繫的地區嗎？
{:faq}

不可以。IBM Cloud 提供兩種選項：(1) 僅限單一地區，或 (2) 所有地區，使用「廣域遞送」附加程式。

## 我使用了 Equinix Cloud Exchange 的 Direct Link 自動化訂購程序，且被指派了與內部網路重疊的子網路怎麼辦？
{:faq}

截至 2018 年三月，建議的最佳作法是取消您的自動化訂購並提供新的問題單，以填寫 Direct Link 問卷。您應該指出您喜好 10.254.x.x 範圍的另一個子網路，還是 172.32.x.x 範圍。

## Direct Link Exchange 和 Direct Link Connect 有什麼差異？
{:faq}

這兩項服務很類似，都相當低成本、容忍延遲，且能快速接觸 IBM Cloud Direct Link 的好處。簡括地說，Exchange 利用資料中心提供者，而 Connect 利用通訊業者。以下是一些額外的詳細資料：

對於偏好在資料中心內利用 Exchange 的客戶，建議使用 **Direct Link Exchange**。使用 Exchange 服務，客戶可以快速地啟用與其主機託管的多雲端連線功能，因為基礎電路已經佈建好（這些其他的雲端提供者必須已在設施內有實體交互連接）。

Direct Link Exchange 容許透過單一雲端交換埠的多雲端共用環境，該環境是由 IBM Cloud 與 Cloud Exchange 服務提供者之間的第 2 層網路至網路 (NNI) 連線所建立。埠速度最高可以達到 1Gb。

**Direct Link Connect** 適合喜好利用自己內部部署與 IBM Cloud 之間現有網路的客戶。使用 Direct Link Connect 服務，客戶可以使用新的及現有的通訊業者網路（例如 MPLS）來快速啟用 IBM Cloud，因為能利用已經預先佈建的基礎電路。

透過 Direct Link Connect，客戶可透過 Connect 提供者、經由「網路至網路 (NNI)」連線來連接至 IBM Cloud，並由全球設施中的 IBM 合作夥伴操作。埠速度最高可以達到 5Gb。

## Direct Link Connect 和 Direct Link Exchange 提供者的比較
{:faq}

Connect 提供者是網路可達到資料中心之外的電信公司。Exchange 提供者限制在資料中心內。兩者都可以為客戶啟用多雲端體驗。Exchange 提供者通常在他們的資料中心裡需要主機託管，而 Connect 提供者可以達到客戶的內部部署網站與資料中心。

## IBM 可以透過 Direct Link 支援 IPv6 嗎？
{:faq}

不適用於 BGP 階段作業。我們必須從 IPv4 中指派我們的 /30，而且我們需要客戶相同的回報。

## IBM 可以在專用網路上執行 IPV6 嗎？
{:faq}

不可以。IPv6 只能公用。

## Verizon SCI 是否有任何特殊 Direct Link 需求？字首 / ASN / VLAN BGP / 等等？
{:faq}

Verizon SCI 是數個 MPLS 型第 3 層 (IP VPN) 服務的其中一個。它需要 IBM 與 Verizon 之間建立 BGP，而不是直接面對客戶。然後，Verizon 與客戶之間建立 BGP，並據此通告路徑。有數個其他基於第 3 層的服務提供者會參與 Direct Link Connect 計劃。客戶需要知道他們訂購什麼，以及連接到 IBM Cloud 時其帳戶要如何處理。

## Direct Link 是否支援任何類型的 QoS？
{:faq}

我們無法支援任何 QoS 保證。QoS 需要我們的每一個服務供應商與 IBM Cloud 之間有 MPLS 對映。「雲端服務提供者」通常無法在此時支援 QoS，因為它必須從頭到尾涵蓋，而且涉及其間的每個裝置。透過「通道作業」或任何其他方法都無法提供暫行解決方法。

## Direct Link 是否支援巨大訊框？
{:faq}

Dedicated 和 Dedicated Hosting 支援巨大訊框（最多 9214 位元組）。
理論上，支援 Connect 和 Exchange 是可行的，但需要服務提供者與 IBM 合作，並確保端對端連線支援「巨大訊框」，包括基礎「網路至網路介面 (NNI)」。依預設，Exchange 及 Connect 已設定為具有 1500 位元組 MTU 支援。

## 使用 Direct Link Connect 時，客戶如何確保透過相同通訊業者的路由器多樣性（範例：DAL03 中的 Verizon）？
{:faq}

我們有不同的 XCR，可為通訊業者建立不同的 NNI 鏈結。從那個點開始，由通訊業者決定是否維持多樣性。

## 若為 Direct Link Connect，客戶是否需要訂購 2 個鏈結以提供備援，或是 Direct Link Connect 原本就提供備援？
{:faq}

訂購 2 個鏈結以提供多樣性。我們並未在交換器或路由器之間提供備援。客戶可在每一個 Direct Link 上建立具有其 BGP 配置的備援。

## 要如何輕鬆升級我的 Direct Link 連線頻寬（例如，從 1GB 升級到 5GB）？
{:faq}

一般而言，我們會在 1G 光學設備上安裝 1G 以下的速度。若為 2G 到 10G 的速度，請安裝 10G 光學設備。因此，從 1G 升級至 5G 將需要指派或插入新的光學設備。它會是影響服務的事件。如果這是您預期的成長類型，則可以要求在 Direct Link 部署之初安裝 10G 光學設備，或一開始就訂購 2G，讓 10G 光學設備就定位。

## ECMP 是處理備援 Direct Link 連線應採取的方法嗎？是否有替代方案？
{:faq}

請注意，ECMP 並不是為了備援連線，而是為了平衡兩個鏈結的負載。透過 ECMP，兩個連線都必須終止回到相同的 IBM Cloud 交叉連接路由器 (XCR)，而使它成為單一失敗點。（換句話說，當兩個階段作業是位於相同的 IBM Cloud XCR 上時，才能佈建 ECMP）。 

ECMP 是 BGP 的一項特性。如果您要尋求備援，請取得兩個 Direct Link 連線，一個連線進入一個 XCR。如果您要使用 ECMP 並具有備援，則您需要每個 XCR 有兩個 Direct Link 連線，這樣您才能同時執行 2 個 ECMP 階段作業。

或者，我們有些客戶將兩個鏈結設定到相同資料中心（例如，WDC02）的不同 XCR，然後視需要使用 BGP 配置進行失效接手。比起將 Direct Link 連線置於兩個不同的資料中心（例如 WDC02 和 WDC05），此配置較少備援（較不安全）。

## 帳戶 BCR 連線的 Direct Link XCR 連線有 SLA 嗎？
{:faq}

目前沒有 Direct Link 的 SLA。客戶實際上可以藉由針對使用 BGP 的失效接手適當配置 2 個以上的 Direct Link 而達到 99.999%，但 IBM 無法控制或提供其 SLA。

## 我可以從哪裡取得設定 Direct Link 的協助？
{:faq}

如需連接至 Direct Link，請參閱[配置 {{site.data.keyword.cloud_notm}} Direct Link](/docs/infrastructure/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-dedicated)。如果您需要其他協助，可以在已開立的問題單裡要求新服務的工程支援。即使是 Equinix 的 API 服務，開立問題單也能讓工程式查看它。或者，您可以與您的 IBM 業務代表聯絡。

## 在 Direct Link Exchange 上，IBM 有設定 BGP 密碼嗎？
{:faq}

依預設，我們不會對 Direct Link Exchange 設定任何 BGP 密碼。可以選擇指定 BGP ASN，然後我們指派 BGP IP 位址。此外，也可以設定 BGP 密碼以進行鑑別，我們只需要讓工程師知道。
