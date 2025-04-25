---

# Mikrotik Cyber Threat Intel

This repository offers a Cyber Threat Intelligence (CTI) feed for MikroTik routers in RSC format. It provides a compact list of malicious IP addresses, designed using AI/ML reinforcement learning to block 60–70% of attacks while minimizing list size, helping to protect your network effectively. 

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

---

You can help improve the effectiveness by alerting us to false positives and false negatives.

---



