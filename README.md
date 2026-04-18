# SDN Network Utilization Monitor

## 1. Introduction

This project implements a Software Defined Networking (SDN) based Network Utilization Monitor using Mininet and the Ryu controller. The system monitors network traffic dynamically by collecting port-level statistics and calculating bandwidth usage in real time.

The project demonstrates key SDN concepts such as centralized control, flow rule installation, and traffic monitoring using the OpenFlow protocol.

---

## 2. Objectives

* Design a custom network topology using Mininet
* Implement an SDN controller using Ryu
* Monitor network traffic using port statistics
* Calculate bandwidth utilization in Mbps
* Analyze network performance under traffic load
# SDN Network Utilization Monitor

## 1. Introduction

This project implements a Software Defined Networking (SDN) based Network Utilization Monitor using Mininet and the Ryu controller. The system monitors network traffic dynamically by collecting port-level statistics and calculating bandwidth usage in real time.

The project demonstrates key SDN concepts such as centralized control, flow rule installation, and traffic monitoring using the OpenFlow protocol.

---

## 2. Objectives

* Design a custom network topology using Mininet
* Implement an SDN controller using Ryu
* Monitor network traffic using port statistics
* Calculate bandwidth utilization in Mbps
* Analyze network performance under traffic load

---

## 3. System Architecture

The system consists of the following components:

* Mininet (network emulator)
* Open vSwitch (data plane device)
* Ryu Controller (control plane logic)
* OpenFlow Protocol (communication between controller and switches)

---

## 4. Network Topology

The custom topology used in this project:

h1 --- s1 --- s2 --- h2

* h1, h2: Hosts
* s1, s2: OpenFlow switches

---

## 5. Working Principle

1. The Mininet topology is created with hosts and switches
2. Switches connect to the Ryu controller
3. Packet-in events are triggered for unknown packets
4. The controller forwards packets and installs flow rules
5. A monitoring thread periodically requests port statistics
6. The controller receives tx_bytes and rx_bytes values
7. Bandwidth is calculated based on byte differences over time

---

## 6. Bandwidth Calculation

Bandwidth is calculated using:

Bandwidth (Mbps) = (Byte Difference × 8) / Time Interval / 10^6

Where:

* Byte Difference = Current bytes − Previous bytes
* Time Interval = Time between measurements

---

## 7. Tools and Technologies

* Python
* Mininet
* Ryu SDN Controller
* Open vSwitch
* OpenFlow 1.3
* iperf
* ping

---

## 8. Execution Steps

### Terminal 1 (Controller)

cd ~
ryu-manager monitor.py

### Terminal 2 (Mininet)

sudo mn -c
sudo mn --custom topo.py --topo monitor --controller remote --switch ovsk,protocols=OpenFlow13

### Inside Mininet

pingall
iperf h1 h2

---

## 9. Output

The controller displays:

* Transmit bandwidth (TX Mbps)
* Receive bandwidth (RX Mbps)
* Port-level traffic statistics

Example:
Switch 1 Port 1: TX = 12.5 Mbps, RX = 10.2 Mbps

---

## 10. Key Features

* Real-time traffic monitoring
* Bandwidth calculation using port statistics
* Custom SDN topology
* OpenFlow-based control

---

## 11. Challenges Faced

* OpenFlow version mismatch
* Packet forwarding issues
* Debugging controller logic

---

## 12. Applications

* Network monitoring
* Traffic analysis
* Data center networking
* SDN research

---

## 13. Future Scope

* Web-based dashboard
* QoS implementation
* Traffic prediction using machine learning

---

## 14. Conclusion

This project demonstrates how SDN can be used for efficient network monitoring. Using Mininet and Ryu, the system provides a flexible and programmable way to analyze traffic and calculate bandwidth in real time.

---

## 15. Author

Yaseen Mulla


