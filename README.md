# SDN Port Monitoring using Ryu and Mininet

##  Project Title

SDN-based Port Monitoring and Failure Detection using Ryu Controller and Mininet

---

##  Description

This project implements a Software-Defined Networking (SDN) based port monitoring system using the Ryu controller and Mininet emulator. The system detects and logs real-time changes in switch port status such as UP and DOWN events.

In SDN, the control plane is centralized in the controller, allowing dynamic monitoring and intelligent decision-making. The Ryu controller listens for OpenFlow port status events and updates the network state accordingly.

Mininet is used to simulate a network topology, and link failures are manually triggered to observe controller behavior.

---

##  Objective

* Monitor port status (UP/DOWN) in real time
* Detect link failures dynamically
* Maintain failure count for each port
* Demonstrate SDN controller–switch interaction

---

##  Tools & Technologies

* Mininet
* Ryu Controller
* OpenFlow Protocol
* Ubuntu / WSL

---

##  Setup Instructions

### 1. Start Ryu Controller

```
~/.pyenv/versions/3.10.13/bin/ryu-manager port_monitor.py
```

### 2. Run Mininet Topology

```
sudo mn --topo single,3 --controller remote --switch ovsk
```

---

##  Execution Steps

### Test Connectivity

```
pingall
```

### Generate Port Events

```
link s1 h1 down
link s1 h1 up
link s1 h2 down
link s1 h2 up
link s1 h3 down
link s1 h3 up
```

### Exit Mininet

```
exit
```

### View Logs

```
cat port_log.txt
```

---

##  Output

* Controller detects port DOWN events and raises alerts
* Port recovery (UP) is logged
* Failure count increases with each failure
* Logs are stored with timestamps

---

##  Analysis

* When a link goes DOWN, the controller immediately detects the failure
* Failure count increases with repeated failures
* Real-time monitoring is achieved through OpenFlow events
* Demonstrates centralized control in SDN

---

## Result

Successfully implemented SDN-based port monitoring and failure detection using Ryu controller and Mininet.

---

##  References

* Ryu Documentation
* Mininet Documentation
* OpenFlow Protocol Specification

---

