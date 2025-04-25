---

# Mikrotik Cyber Threat Intel

This repository provides a compact Cyber Threat Intelligence (CTI) feed for Mikrotik routers in RSC format. Powered by AI/ML reinforcement learning, it delivers a minimal list of malicious IP addresses that blocks 60–70% of attacks. The small size ensures compatibility with most Mikrotik models and uses minimal CPU resources, making it an efficient security solution for your network. This is "Security for the 99%"

---

### Script Contribution

*Contributed by:* **JayR Baldeva**

---

### Prerequisites

- Download the `WatchDogBlocklist-current.rsc` file to your desktop.
- If needed, rename the file to `WatchDogBlocklist-current.rsc`.
- Then Upload the file to your Mikrotik router.

---

### Installation

Import the blocklist file into your Mikrotik router using the following command:

```shell
/import file-name=WatchDogBlocklist-current.rsc
```

---

### Firewall Rules

Add the following firewall filter rules to drop connections from IPs listed in the WatchDogBlocklist:

```plaintext
/ip firewall filter

add action=drop chain=forward comment="Blocklist Forward"  dst-address-list=WatchDogBlocklist log=yes log-prefix=blocklist
add action=drop chain=input comment="Blocklist Input" log=yes  src-address-list=WatchDogBlocklist log-prefix=blocklist
```

You can delete the old list with this command: 
```plaintext
/ip firewall address-list remove [find where list="=WatchDogBlocklist"]
```
---

Please help improve the effectiveness by alerting us to false positives and false negatives.

---



