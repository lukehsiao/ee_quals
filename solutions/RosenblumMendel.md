# Mendel Rosemblum Solutions

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Mendel Rosemblum Solutions](#mendel-rosemblum-solutions)
	- [2008 Question](#2008-question)

<!-- /TOC -->

## 2008 Question
1. If Channel 2 has a bandwidth problem, I would expect that Channel 1 utilization would be 100%, while all of the other observation points are low utilization. The justification being that Box B is getting requests very slowly, box A is usually just waiting to use the channel, and channel 2 is occasionally transferring a response from B. Most of the time, it seems that everyone would be waiting.

2. If there is a latency problem, I would expect all observation points to exhibit bursty behavior.

3. To address bandwidth problems, techniques like compression could be used for the requests to reduce the amount of data that needed to be sent (assuming the requests are highly compressable). Similarly if there was only a few requests, we could encode requests more efficiently (e.g. send '1', rather than 'Give me your IP address'). If the software could be benefitted by this, we could also structure the code so that requests are sent very early and other processing is done while waiting for a response. We may also be able to create caches that allow us to reduce the number of requests that actually need to be sent to box B.

4. This would not help with bandwidth. However, it would help with latency.
