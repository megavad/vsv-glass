---
title: Идея
permalink: /projs_ru/gw/idea/
position: 1
#redirect_from:
#  - /
#  - /docs/quickstart/
#  - /docs/extras/
---
Main idea was to remove Mitsubishi PLC from dataflow chain.


Pilot project is based on computers with Windows XP embedded as Inspection system core, and line PLC - Siemens with communication processor dedicated for this task.

Our application (GW) should read all traffic from inspection application(APP), running on "Main PC", to RS232 via Melsec protocol, extract necessary bits and bytes and send it via socket to Siemens (PLC). Also GW should answer to APP with watchdog bit (it should be changed once per 500ms).

{::nomarkdown}
<img src="/img/gw_simplified.svg">
{:/}



First of all we need to sniff some traffic and analyze typical dataflow. Below you could see example of data from remote PC to Mitsubishi PLC


{% raw %}
```cpp
25	0.00000838	AgsMHP.exe	IOCTL_SERIAL_SET_BAUD_RATE	Serial0	SUCCESS	Rate: 9600
26	0.00000587	AgsMHP.exe	IOCTL_SERIAL_SET_RTS	Serial0	SUCCESS		
27	0.00000587	AgsMHP.exe	IOCTL_SERIAL_SET_DTR	Serial0	SUCCESS		
28	0.00000419	AgsMHP.exe	IOCTL_SERIAL_SET_LINE_CONTROL	Serial0	SUCCESS	StopBits: 1 Parity: ODD WordLength: 8
29	0.00000335	AgsMHP.exe	IOCTL_SERIAL_SET_CHAR	Serial0	SUCCESS	EOF:0 ERR:0 BRK:0 EVT:0 XON:11 XOFF:13
30	0.00000503	AgsMHP.exe	IOCTL_SERIAL_SET_HANDFLOW	Serial0	SUCCESS	Shake:1 Replace:40 XonLimit:2048 XoffLimit:512
31	0.00000335	AgsMHP.exe	IOCTL_SERIAL_SET_QUEUE_SIZE	Serial0	SUCCESS	InSize: 1024 OutSize: 1024
```
{% endraw %}
{: .note}
тест
