---
title: Engineering
permalink: /projs/gw/engineering/
position: 2
#redirect_from:
#  - /
#  - /docs/quickstart/
#  - /docs/extras/
---

All data we need stored in the ini file of APP. We have two apps - for Main PC and for Remote PC. To reduce details - tasks were very closed to each other and we will review solution for Main PC only.


First of all we need to sniff some traffic and analyze typical dataflow. Below you could see example of traffic from remote PC to Mitsubishi PLC - establishing communication.


{% raw %}
```cpp
25	0.00000838	AgsMH.exe	IOCTL_SERIAL_SET_BAUD_RATE	Serial0	SUCCESS	Rate: 9600
26	0.00000587	AgsMH.exe	IOCTL_SERIAL_SET_RTS	Serial0	SUCCESS		
27	0.00000587	AgsMH.exe	IOCTL_SERIAL_SET_DTR	Serial0	SUCCESS		
28	0.00000419	AgsMH.exe	IOCTL_SERIAL_SET_LINE_CONTROL	Serial0	SUCCESS	StopBits: 1 Parity: ODD WordLength: 8
29	0.00000335	AgsMH.exe	IOCTL_SERIAL_SET_CHAR	Serial0	SUCCESS	EOF:0 ERR:0 BRK:0 EVT:0 XON:11 XOFF:13
30	0.00000503	AgsMH.exe	IOCTL_SERIAL_SET_HANDFLOW	Serial0	SUCCESS	Shake:1 Replace:40 XonLimit:2048 XoffLimit:512
31	0.00000335	AgsMH.exe	IOCTL_SERIAL_SET_QUEUE_SIZE	Serial0	SUCCESS	InSize: 1024 OutSize: 1024
```
{% endraw %}

{: .note}
Thanks to sysinternals - I have good instruments to do this job.
[Sysinternals ]({{ 'https://docs.microsoft.com/en-us/sysinternals/' | absolute_url }})

Then I have done a dictionary (from ini file) with registers, and a data that should be stored into registers.

Application consists from 2 threads: one is for serving APP data from virtual com port, and another is for socket to Siemens to synchrinize data with line PLC. This is console application with some debug output to its window only (Embedded XP should not use storage for writing operations).

Serving APP data is to parce
[Melsec ]({{ 'https://dl.mitsubishielectric.com/dl/fa/document/manual/plc/sh080008/sh080008ab.pdf' | absolute_url }}) protocol, extract what register we should send (from APP to PLC) or receice(from PLC(actually - our synchonized with PLC dictionary) to APP) its data.
{::nomarkdown}
<img src="/img/gwarchitecture.svg">
{:/}

Then autostart for virtual com port service and GW app is added to Windows, and socket reconnection procedure in case of communication failures added.

That is all, thank you.
