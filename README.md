## Network-traffic-analysis
This project is based on analyzing window host to identify the **RAT** infection. by leveraging wireshark custom profiles and advanced filters.

---

### Lab Environment
**Tools**: Wireshark, OSINT(virusTotal)

**Dataset**: 2024-11-26-traffic-analysis-exercise.pcap

**Protocol Analyzed**: HTTP/HTTPS, DNS, LDAP, TCP/IP

### Investigation Phase 1 Traffic Normalization and Surface analysis
- **Goal**: reduce traffic noise and identified host and primary C2 infrastructure
- **Action**: applied a custom *Basic web filter* to remove **SSDP** which increase noise
  - `(http.request or tls.handshake.type eq 1) and !(ssdp)`
- **Discovery**: identified victim host ``
