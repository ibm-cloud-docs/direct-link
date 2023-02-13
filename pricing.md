---

copyright:
  years: 2018, 2023
lastupdated: "2023-02-13"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Pricing for {{site.data.keyword.cloud_notm}} Direct Link on Classic
{: #pricing-for-ibm-cloud-direct-link}

Pricing for Direct Link Connect, Dedicated, and Exchange "on Classic" offerings is consistent for equivalent regions and bandwidth, as shown in the following monthly pricing tables.
{: shortdesc}

The published pricing is for estimate purposes only. IBM must check with the colocation provider for firm pricing and availability. Also, Direct Link on Classic pricing does NOT include the additional charges by service providers to enable connectivity to {{site.data.keyword.cloud_notm}}.
{: note}

You, the customer, must arrange connectivity and billing with your service providers, independently of {{site.data.keyword.cloud_notm}}. See the list of Exchange and Connect providers at [IBM Cloud Direct Link Partners](https://www.ibm.com/cloud/direct-link/partners). Direct Link Dedicated creates a Letter Of Authorization / Connecting Facility Assignment (LOA/CFA), which is usable by any service provider who can reach the **Meet Me Room that is specified** on that LOA/CFA. The provider who is connecting to the LOA/CFA must include pricing for the cross-connect in their quote to you; {{site.data.keyword.cloud_notm}} does not order cross-connects on behalf of any customer.
{: important}

## Pricing table
{: #pricing-table}

Select a tab in the table to view pricing for Direct Link on Classic offerings:

| Region | 50 Mbps | 100 Mbps | 200 Mbps | 500 Mbps | 1 Gbps | 2 Gbps | 5 Gbps |
|----|----|----|----|----|----|----|----|
| US | $100 | $150 | $300 | $650 | $1,199 | $1,999 | $3,750 |
| Canada / Amsterdam | $103 | $155 | $309 | $670 | $1,235 | $2,059 | $3,863 |
| London / Norway | $107 | $161 | $321 | $696 | $1,283 | $2,139 | $4,013 |
| Paris / Frankfurt / Milan / Korea | $110 | $165 | $330 | $715 | $1,319 | $2,199 | $4,125 |
| Japan / Singapore / Hong Kong | $113 | $170 | $339 | $735 | $1,355 | $2,259 | $4,238 |
| Australia / Brazil / India | $120 | $180 | $360 | $780 | $1,439 | $2,399 | $4,500|
{: class="simple-tab-table"}
{: caption="Table 1. Direct Link Connect on Classic" caption-side="bottom"}  
{: #simpletabtable1}
{: tab-title="Connect on Classic"}
{: tab-group="IAM-simple"}

| Region | 1 Gbps | 2 Gbps | 5 Gbps | 10 Gbps |
|----|----|----|----|----|
| US | $1,199 | $1,999 | $3,750 | $4,999 |
| Canada/Amsterdam | $1,235 | $2,059 | $3,863 | $5,149 |
| London / Norway| $1,283 | $2,139 | $4,013 | $5,349 |
| Paris / Frankfurt / Milan / Korea | $1,319 | $2,199 | $4,125 | $5,499 |
| Japan / Singapore / Hong Kong | $1,355 | $2,259 | $4,238 | $5,649 |
| Australia / Brazil / India | $1,439 | $2,399 | $4,500| $5,999 |
{: #simpletabtable2}
{: caption="Table 2. Direct Link Dedicated on Classic" caption-side="bottom"}  
{: tab-title="Dedicated on Classic"}
{: tab-group="IAM-simple"}
{: class="simple-tab-table"}

| Region | 50 Mbps | 100 Mbps | 200 Mbps | 500 Mbps | 1 Gbps |2 Gbps | 5 Gbps |
|----|----|----|----|----|----|----|----|
| US | $100 | $150 | $300 | $650 | $1,199 | $1,999 | $3,750 |
| Canada / Amsterdam | $103 | $155 | $309 | $670 | $1,235 | $2,059 | $3,863 |
| London / Norway| $107 | $161 | $321 | $696 | $1,283 | $2,139 | $4,013 |
| Paris / Frankfurt / Milan / Korea | $110 | $165 | $330 | $715 | $1,319 | $2,199 | $4,125 |
| Japan / Singapore / Hong Kong | $113 | $170 | $339 | $735 | $1,355 | $2,259 | $4,238 |
| Australia / Brazil / India | $120 | $180 | $360 | $780 | $1,439 | $2,399 | $4,500|
{: #simpletabtable3}
{: caption="Table 3. Direct Link Exchange on Classic" caption-side="bottom"}  
{: tab-title="Exchange on Classic"}
{: tab-group="IAM-simple"}
{: class="simple-tab-table"}

## Local routing
{: #local-routing}

Local routing is included with all {{site.data.keyword.cloud_notm}} Direct Link offerings. It includes access to all of the data centers connected directly to the local market, and it provides unlimited ingress and egress traffic across the Direct Link. If you need to route your traffic outside the local markets defined in the next section, you must add the Global routing option. Local routing does not incur any overage fees.

## Expanded IBM Direct Link local markets
{: #expanded-ibm-cloud-direct-link-local-markets}

To reach {{site.data.keyword.cloud_notm}} resources outside of the local market in which the Direct Link is connected (at a PoP or data center), you must add the Global routing option, which expands your access to include all {{site.data.keyword.cloud_notm}} data centers, globally.

However, we have expanded our Direct Link local markets to provide more local routing options to our customers across the globe. The local market assignments are listed in the following table.

| Local Market | Sites |
|--------|----------------------|
| US South (Dallas) | DAL02, DAL03, DAL04, DAL07, DAL09, DAL12, DAL13, Denver 1, Chicago 1 |
| San Jose | SJC01, SJC02, SJC03, SJC04, Los Angeles 1 |
| Seattle | SEA02 |
| US East (Washington, D.C.) | WDC01, WDC02, WDC04, WDC05, WDC06, WDC07, Atlanta 1, Miami 1, New York City 2, New York City 3 |
| Montreal | MON01, MON02 |
| Toronto | TOR01, TOR02 |
| Sao Paulo | SAO01, SAO02 |
| Amsterdam | AMS02, AMS03 |
| EU Central (Frankfurt) | FRA01, FRA02, FRA03, FRA04, FRA05 |
| UK South (London) | LON01, LON02, LON03, LON04, LON05, LON06 |
| Milan | MIL01, MIL02 |
| Paris | PAR01, PAR02 |
| Chennai | CHE01, Mumbai 1 |
| Hong Kong | HKG01, HKG03 |
| Singapore | SNG01, SNG02 |
| AP South (Sydney) | MEL02, Perth 1, SYD01, SYD02, SYD03, SYD04, SYD05 |
| AP North (Tokyo) | SEO02, TOK01, TOK02, TOK03, TOK04, TOK05, Osaka 1 |
{: caption="Table 6: Local Markets and Sites" caption-side="bottom"}

For example, in the US South Market, Direct Link customers can send or retrieve data to or from any {{site.data.keyword.cloud_notm}} location in the defined market (Dallas, Houston, Denver, and Chicago) without the need for the global routing add-on.

## Pricing for the global routing add-on
{: #pricing-for-global-routing-add-on}

Global routing expands access to include all {{site.data.keyword.cloud_notm}} data centers globally. Bandwidth is unmetered and charged monthly based on the market. Details on the markets and other considerations can be found in our [FAQs](/docs/direct-link?topic=direct-link-faqs).

| Region | 50 Mbps | 100 Mbps | 200 Mbps | 500 Mbps | 1 Gbps | 2 Gbps | 5 Gbps | 10 Gbps |
|----|----|----|----|----|----|----|----|----|
|US | $150 | $300 | $600 | $1,500 | $3,000 | $4,000 | $4,500 | $5,000 |
|Canada/Amsterdam | $155 | $309 | $618 | $1,545 | $3,090 | $4,120 | $4,635 | $5,150 |
|London/Norway | $161 | $321 | $642 | $1,605 | $3,210 | $4,280 | $4,815 | $5,350 |
|Paris/Frankfurt/Milan/Korea | $165 | $330 | $660 | $1,650 | $3,300 | $4,400 | $4,950 | $5,500 |
|Japan/Singapore/Hong Kong | $170 | $339 | $678 | $1,695 | $3,390 | $4,520 | $5,085 | $5,650 |
|Australia/Brazil/India | $180 | $360 | $720 | $1,800 | $3,600 | $4,800 | $5,400 | $6,000 |
{: caption="Table 7: Pricing for the global routing add-on" caption-side="bottom"}

## Additional fees for customization
{: #additional-fees-for-customization}

Several customized, non-standard configurations are available for extra cost. Most of the fees are one-time fees for setup, denoted by "NRC" in the table. These options require an Exception review by the offering management (OM) and Special Network Services (SNS) teams before approval.

| Type of service | Fee |
|-----------------|------|
| SNS fee | $3000 MRC (monthly) per Account |
{: caption="Table 8: Additional fees for customization" caption-side="bottom"}
