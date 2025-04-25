---

# Mikrotik Cyber Threat Intel

This repository provides a Cyber Threat Intelligence script for Mikrotik routers in RSC format.

---

### Script Contribution

*Contributed by:* **JayR Baldeva**

---

### Prerequisites

- Download the `WatchDogBlocklist-current.rsc` file to your desktop.
- If needed, rename the file to `WatchDogBlocklist-current.rsc`.

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

add action=drop chain=forward comment="Blocklist Forward" dst-address-list=bnsblocklist log=yes log-prefix=blocklist
add action=drop chain=input comment="Blocklist Input" log=yes log-prefix=blocklist src-address-list=bnsblocklist
```

---

This setup helps protect your Mikrotik router by blocking traffic from known malicious IP addresses.

---



