---
title: Initial technical solution
permalink: /projs/insp_proj/initial_solution/
position: 1
---

Initial soultion was based on data that application (APP) could receive from Sick MLG2 sensor bar (MLG) via Ethernet/IP(with cifX 50E-RE PCIE card) every 10ms and encoder + glass sensor data via IO PCIE board from Advantech (PCI-1884).

Ethernet/IP protocol was initially in solution because of PLC-based pre-solution.

Pilot solution consists of 6 parts:
- GUI with current NC-file reading and visualization (every 1 sec)
- Ethernet/IP CIP message handler thread (continuous)
- PCIE-1884 (Advantech) encoder counlter/Digital Input handler thread (every 1ms)
- VSM cutting app log reading thread (if new NC file opened and sent to work by operator), every 30 seconds
- SLC 5/05 signal handler thread (every 100 ms)
- calculation thread (event-based)
Because of slow delivery of cards deep investigation of CIP session establishing done.
Switching Windows timer to high resolution (from 15ms to 1ms) lets to solve Ethernet/IP task without cifX 50E-RE PCIE card (we need to receive UDP messages from MLG every 10ms to achieve necessary resolution).

Advantech Spartan-6 based IO card was also not good solution because of a bug (value -1 on every counter channel even if we do not use it, and no reaction on any event after that until you switch off this device in Device Manager and turn on again) and no reaction from official support - we decide not to use Advantech cards due to terrible support.
