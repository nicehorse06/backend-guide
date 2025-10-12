## 🌐 Network

### OSI Model (7 Layers)
- L1: Physical Layer — Cables, fiber, NIC, bit transmission
- L2: Data Link Layer — MAC address, Ethernet frame, Switch, VLAN, 802.1Q tagging
- L3: Network Layer — IP addressing, Subnet mask, CIDR, Routing, ARP, ICMP, TTL
  - IP Concepts
    - Net_ID vs Host_ID
    - Private IP vs Public IP
    - Netmask, Broadcast, Gateway
    - IPv4 vs IPv6
- L4: Transport Layer — TCP, UDP, Ports, Connection State
  - TCP: Three-way handshake, Sliding Window, Congestion Control
  - UDP: Connectionless, Datagram
- L5–L7: Session / Presentation / Application
  - SSL/TLS Handshake
  - HTTP / DNS / SMTP / SSH / WebSocket

---

### TCP / UDP
- TCP Flags (SYN, ACK, FIN, RST)
- Connection Establishment & Termination
- TCP Retransmission, Timeout
- UDP Characteristics
- Port Ranges (Well-known / Ephemeral)

---

### DNS (Domain Name System)
- DNS Record Types (A, AAAA, CNAME, MX, TXT, PTR, SRV)
- Recursive vs Authoritative Resolver
- TTL & Caching
- DNS over HTTPS (DoH) / DNS over TLS (DoT)
- Split-horizon DNS / Private Hosted Zone

---

### Routing / Gateway
- Default Gateway
- Static vs Dynamic Routing
- Routing Table (`ip route`, `netstat -rn`)
- Policy Routing / Multiple Tables
- ICMP Redirect
- Traceroute / Path MTU Discovery
- NAT (SNAT, DNAT, MASQUERADE, PAT)

---

### CDN (Content Delivery Network)
- Edge Node / PoP
- Caching / TTL / Invalidation
- Geo-DNS / Anycast
- CDN vs Reverse Proxy

---

### HTTP / Web
- HTTP Methods: GET, POST, PUT, PATCH, DELETE, OPTIONS
- HTTP Status Codes (1xx–5xx)
- HTTPS / SSL / TLS Handshake
- RESTful API Design
- HTTP Headers
- HTTP Caching (ETag, Cache-Control, Expires)
- HTTP Compression (gzip, br)
- HTTP/2 and HTTP/3 (QUIC)
- CORS (Cross-Origin Resource Sharing)
- MIME Types / Content-Type
- Cookie / Session / Token / SameSite

---

### Load Balancer / Proxy
- Reverse Proxy vs Forward Proxy
- Layer 4 (TCP) vs Layer 7 (HTTP) Load Balancing
- Common Algorithms: Round Robin, Least Connections, IP Hash, Weighted
- Sticky Session / Session Affinity
- Health Check / Failover
- Nginx / HAProxy / Envoy / Traefik
- API Gateway Concept
- Reverse Proxy Caching

---

### Real-Time Communication
- Polling / Long-Polling
- Server-Sent Events (SSE)
- WebSocket / Socket.io
- WebRTC
- gRPC Streaming
- MQTT (IoT Protocol)

---

### 🔧 Linux Networking
- Network Interface (`ip link`, `ifconfig`)
- IP Address Management (`ip addr`)
- Routing (`ip route`)
- Network Namespace (`ip netns`)
- veth Pair / Bridge / Bond / VLAN / macvlan / ipvlan
- Loopback Interface
- sysctl Parameters (`net.ipv4.ip_forward`, `rp_filter`, `tcp_tw_reuse`)
- Firewall: iptables / nftables
  - Netfilter Hooks: PREROUTING, INPUT, FORWARD, OUTPUT, POSTROUTING
  - NAT Table (SNAT, DNAT, MASQUERADE)
- Traffic Control (tc / qdisc / QoS)
- Packet Capture: tcpdump, Wireshark
- Connection Tracking: conntrack
- Debug Tools: netstat, ss, lsof, iperf, curl, ping, traceroute

---

### ☁️ Cloud Networking (AWS / GCP / Azure)
- VPC / Subnet / Route Table
- Internet Gateway (IGW) / NAT Gateway
- Security Group vs Network ACL
- Elastic IP / Elastic Network Interface (ENI)
- PrivateLink / VPC Endpoint
- VPC Peering / Transit Gateway
- Load Balancer (ALB / NLB)
- Route53 / Private Hosted Zone
- VPN / Direct Connect
- CIDR Design for Multi-Subnet Architecture

---

### ☸️ Kubernetes Networking
- CNI (Container Network Interface)
- Pod-to-Pod Networking (flat network model)
- Service Types: ClusterIP / NodePort / LoadBalancer / ExternalName
- kube-proxy / iptables / IPVS
- NetworkPolicy (Ingress / Egress)
- DNS in Cluster (CoreDNS)
- Overlay Network: VXLAN / Geneve
- CNI Plugins: Flannel, Calico, Cilium, Kube-OVN, Weave
- Multus / SR-IOV for multi-NIC / VM integration
- Ingress Controller (Nginx, Traefik, Envoy)
- Service Mesh (Istio, Linkerd, Cilium Service Mesh)

---

### 🧰 Performance & Debugging
- MTU / MSS / Fragmentation
- Latency vs Throughput
- Bandwidth / RTT / Packet Loss
- Connection Tracking Table
- tcpdump / ss / netstat / conntrack / iperf
- DNS Lookup Delay
- Network Queues: tx_queue / rx_queue
- eBPF / XDP for packet tracing
- Monitoring: Prometheus / Grafana / Netdata

---

### 🔒 Network Security
- Firewall Rules / ACL
- Stateful vs Stateless Filtering
- Intrusion Detection (IDS) / Intrusion Prevention (IPS)
- DDoS Mitigation
- TLS Certificates / PKI / CA
- VPN (IPsec, WireGuard, OpenVPN)
- Security Hardening: `fail2ban`, `ufw`
- Security Group (AWS)
- Zero Trust / mTLS / Service Mesh Security
- HTTPS HSTS / CSP / CORS Security Headers

---

### 🧱 Advanced Networking Topics
- NAT vs PAT
- Port Forwarding / Hairpin NAT
- ARP Table / Neighbor Table
- Proxy ARP / Gratuitous ARP
- VRRP / Keepalived
- OSPF / BGP Basics
- VLAN Trunking
- Bonding / Link Aggregation (LACP)
- Overlay Network (VXLAN, GRE)
- SDN / Open vSwitch / OVN
- Policy Routing / fwmark
- ip rule / multiple routing tables

---

### 🧩 Tools & Utilities
- `ip`, `ethtool`, `arp`, `route`, `bridge`, `brctl`
- `tcpdump`, `ss`, `conntrack`, `nmap`, `ping`, `traceroute`
- `curl`, `wget`, `dig`, `nslookup`
- `iptables`, `nft`, `ufw`, `firewalld`
- Performance: `iperf`, `ab`, `wrk`, `netperf`
- Visualization: Wireshark, termshark, bmon, iftop

---

### 📦 Related Concepts for Backend Devs
- API Gateway vs Load Balancer
- CDN vs Edge Server
- Proxy vs Reverse Proxy
- NAT Gateway vs Bastion Host
- TLS Termination / Offloading
- Service Mesh Data Plane / Control Plane
- Sidecar Proxy
- Connection Pooling
- Web Performance (TTFB, latency, caching)

---
