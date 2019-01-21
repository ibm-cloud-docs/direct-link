---
copyright:
  years: 1994, 2017, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Understanding Latency

_Go Hybrid with {{site.data.keyword.cloud}} Direct Link: making your workloads run faster, worldwide_

IBM Cloud offers data centers with Direct Link capabilities around the globe. Therefore, you can count on minimal latency when you use Direct Link to create your Hybrid cloud solution by linking your IBM Cloud to your existing infrastructure.

Whether you have an online store, run big data solutions, or have your employees set up on a network with access to files around the world—you never want to hear that slow page loading on the web, or slow data transfer from a database, is keeping you from a sale or reducing employee productivity. Slowdowns can be caused by network latency, which is the measurement of how quickly data travels between two connected points on the internet. You can think of it as the amount of time it takes for one packet of data to get from one place to another.

Globally, the internet’s overall latency can vary significantly—depending on how far the data must travel physically, how many times the data has to hop between service providers, how much bandwidth is available along the way, what other data is traveling across the same path, in addition to other variables. IBM Cloud Direct Link offers deterministic latency with greater security, relative to the Internet for predictable performance.


## Understanding Network Latency

As a best practice, every network provider wants to offer the lowest network latency to the greatest number of customers, and every customer wants to obtain the lowest possible latency. It’s a desirable, shared outcome.

Theoretically, data can travel at the speed of light across optical fiber network cables, but for all the reasons just given, data typically travels much more slowly. For example, if a particular network connection has reached its bandwidth capacity, data packets might temporarily queue up to wait for their turn to travel across that pathway. As another example, if a particular service provider’s network selects a network route that is not optimal, data packets can be sent hundreds or thousands of miles away from their destination in the process of getting to their destination! These kinds of delays and detours are the causes of higher network latency—and slower data transfers.

We express network latency in milliseconds (that’s 1,000 milliseconds per second). A few thousandths of a second may not mean much to us as we’re living our daily lives, but milliseconds often become a deciding factor in our web browsing or in our business transactions. For example, in the financial sector, milliseconds can mean billions of dollars of difference in gains or losses from trade transactions on a day-to-day basis.

## Common Approaches that Minimize Network Latency

Given that our shared goal is to minimize latency, it makes sense to limit the number of potential variables that can affect the speed of the data’s movement. No provider can achieve complete control over how data travels across the Internet, but here are some best practices to minimize network latency:

 * Distribute data around the world: Customers in different locations can pull data from a location that’s geographically close to them. Because the data is closer to the customers, it is handed off fewer times. When data has a shorter distance to travel, routing is less likely to cause a significant performance impact.

 * Provision servers with high-capacity network ports: Huge volumes of data can travel across a server every second. If packets are delayed due to fully saturated ports, milliseconds of time pass, pages load more slowly, download speeds drop, and users become unhappy.

 * Understand how your providers route traffic: When you know more details about how your data is transferred to customers around the world, you can make better decisions about where you host your data.

## How IBM Cloud Minimizes Network Latency

To minimize latency, IBM Cloud took a unique approach to building our network. All of our data centers are connected to network points of presence (PoPs), and all of our network points of presence are connected to each other through our global backbone network. Because we maintain our own global backbone network, our network operations team can control network paths and data transfers more precisely than if we relied on other providers to move data between geographies.
 
For example, if an IBM Cloud customer in Berlin wants to watch a cat video hosted on an IBM Cloud server in Dallas, the packets of data that make up that cat video will travel across our backbone network (which is exclusively used by IBM Cloud traffic) to Frankfurt, where the packets are sent to one of our peering or transit public network Service Providers, finally to get to the user in Berlin. Even better, if our customer uses IBM Cloud CDN capability, the packets will be sent from an edge server located close to the customer, and they never need to be sent from Dallas at all.

Without a global backbone network, the video packets are sent to a peering or transit public network provider in Dallas, then that provider routes the packets across its network or sends the packets to another provider at a network hop, and the packets finally bounce their way to Germany. It’s entirely possible that the packets could get from Dallas to Berlin with the same network latency without using the global backbone network, but without the global backbone network, more variables exist; the total latency is much more difficult to guarantee or predict.

Along with using our own global backbone network, IBM Cloud also segments public, private, and management traffic onto different network ports. That means that different types of traffic are transferred without interfering with one another.

## Summary: Network Latency

Your customers want your data as quickly as you can get it to them. The time it takes for your data to get to them across the Internet is called network latency. The more control you have over your data’s network path, the more consistent (and lower) your network latency can be.

* With Direct Link, we give you control over the path your data travels, so your data’s travel will not be interrupted or blocked by other traffic.

* IBM Cloud offers industry-leading Service Providers-- providing high performance, security, and resiliency.

* At IBM Cloud, we continue to add network Points of Presence (PoPs) across the globe to bring your customers’ data closer to your customers-- thereby improving latency and overall performance to meet the needs of your hybrid cloud workloads.

