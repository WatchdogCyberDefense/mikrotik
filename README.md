Certainly! Here's a polished and professional version of your GitHub README content for the Mikrotik Cyber Threat Intel script:

---

# Mikrotik Cyber Threat Intel

This repository provides a Cyber Threat Intelligence script for Mikrotik routers in RSC format.

---

### Script Contribution

*Contributed by:* **JayR Baldeva**

---

### Prerequisites

- Download the `WatchDogBlocklist.rsc` file to your desktop.
- Rename the file to `WatchDogBlocklist-current.rsc`.

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

add action=drop chain=forward connection-state=new log-prefix=blocklist src-address-list=WatchDogBlocklist

add action=drop chain=input connection-state=new log-prefix=blocklist src-address-list=WatchDogBlocklist
```

---

This setup helps protect your Mikrotik router by blocking traffic from known malicious IP addresses.

---

This layout improves readability by using clear sections, code blocks, and concise instructions, making the README look professional and user-friendly.

---

