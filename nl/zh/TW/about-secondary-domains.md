---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# About Secondary Domains

A secondary domain is a domain that {{site.data.keyword.BluSoftlayer_notm}} DNS servers transfer from your server to our Authoritative DNS servers, `ns1.softlayer.com` and `ns2.softlayer.com`.  You can configure a secondary domain in the portal by clicking on **<span style="text-decoration: underline">Domain Name System</span>** in the **<span style="text-decoration: underline">Public Network</span>** folder in the Portal, clicking on the **<span style="text-decoration: underline">Secondary DNS</span>** link, and finally, clicking on **<span style="text-decoration: underline">Add Secondary DNS Record</span>**.

To set up a secondary domain, you'll need three pieces of information: the domain, the *IP address of the master DNS server* we're transferring from and how often, in minutes, you'd like the domain transferred.<br/>
Once a secondary domain is configured, you'll have the ability to change the master server's IP address and the transfer interval.  You will also be able to view the domain as we're transferring, request a manual transfer, convert your secondary domain to a primary domain, and view any error messages we logged during the transfer process.
