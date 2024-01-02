# Route53

EC2, ELB, S3, CloudFront와 연동 가능한 DNS 서비스

DNS서비스는 도메인에 연결된 IP주소를 전달

일반적인 DNS 서비스 : 하나의 주소를 전달

> Route53 : 각 상황에 따라 다른 주소를 전달할 수 있는 여러 기능을 탑재

- Latency Based Routing : 현재 위치에서 지연시간이 가장 낮은 리전의 IP주소를 전달 

    지연시간이 낮다 : 위치가 가장 가깝고 속도가 빠르다

    AWS 글로벌 인프라가 있기때문에 가능

- Weight Round Robin : 서버 IP 주소나 도메인 (ELB)마다 가중치를 부여하여 트래픽을 조절 하는 기능

- DNS Failover : 장애가 발생한 서버의 IP주소/ 도메인은 전달X

- Geo Routing : 지역별로 다른 IP주소를 전달

- CloudFront / S3와 연결할 때 ZoneApex을 지원 

    루트 도메인에 연결 가능 



> ZoneApex : 루트 도메인/NakedDomain 서브도메인이 붙지 않은 상태 ->  www.example.com 경우 example.com

> [요금표](https://aws.amazon.com/ko/route53/pricing/)

