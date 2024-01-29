# Network Load Balancer

네트워크 로드 밸런서(v2)
- 네트워크 로드 밸런서(레이어 4)
- TCP 및 UDP 트래픽을 인스턴스로 전달
- 초당 수백만 건의 요청 처리
- 짧은 지연 시간 ~100ms(ALB의 경우 400ms)
- NLB는 AZ당 하나의 고정 IP를 가지며 탄력적 IP 할당을 지원(특정 IP를 화이트리스트에 추가하는 데 유용함).
- NLB는 최고의 성능, TCP 또는 UDP 트래픽에 사용
- AWS 프리 티어에는 포함되지 않음

## Network Load Balancer – Target Groups
- EC2 instances
- IP Addresses – must be private IPs
- Application Load Balancer
- Health Checks support the TCP, HTTP and HTTPS Protocols