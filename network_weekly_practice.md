
# 네트워크 실습 커리큘럼 (Week-by-Week)

## Week 1 — Intro & Layering
### 실습
- `curl -v https://naver.com` 으로 layer별 헤더 관찰
- `tcpdump -i any port 443` 로 패킷 흐름 캡처
- Layer별 문제 발생시 증상 정리

---

## Week 2 — HTTP & DNS
### HTTP 실습
```
curl -I https://google.com
curl -H "User-Agent: suupponAI" https://httpbin.org/headers
```

### DNS 실습
```
dig google.com
dig txt google.com
dig cname www.netflix.com
```

---

## Week 3 — Reliable Transport, TCP, Congestion
### 실습
- Wireshark: SYN, SYN/ACK, ACK 관찰
- TCP/UDP Echo server 코드 작성
- `iperf3` 로 congestion control 비교
```
sysctl -w net.ipv4.tcp_congestion_control=bbr
```

---

## Week 4 — IPv4, NAT, IPv6
### 실습
- `/24`, `/28` 서브넷 계산 및 veth NIC 구성
- Docker NAT 테이블 확인: `iptables -t nat -L`
- IPv6 ping: `ping6 ipv6.google.com`

---

## Week 5 — Router Internals, Routing Algorithms, BGP
### 실습
- 라우팅 테이블 추가/삭제: `ip route add/del`
- Docker + FRR 로 3-router mini BGP lab 구성
- Prefix hijack 관찰

---

## Week 6 — Broadcast, MAC, Ethernet
### 실습
- `tcpdump broadcast` 패킷 캡처
- Wireshark에서 Ethernet frame header 분석
- ARP 테이블 관찰: `ip neigh`

---

## Week 7 — Encryption, Anonymity, Authentication
### TLS handshake 관찰
```
openssl s_client -connect google.com:443 -tls1_2
```

### 인증 실습
- JWT 기반 인증 서버 구현
- Self-signed TLS cert 생성 및 FastAPI 적용

---

## Week 8 — Mobility
### 실습
- AP 전환 중 ping 유지/끊김 관찰
- RTT 변화 그래프화
- Edge device reconnect 로직 작성

---

# Capstone Project
## Multi-protocol Edge AI Network
- Camera → RTSP
- Sensor → MQTT
- Result → WebSocket/SSE
- Control → REST
- Auth → JWT
- Mobility → reconnect logic
