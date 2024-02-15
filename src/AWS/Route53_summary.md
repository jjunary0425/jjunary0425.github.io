# Route53

고가용성, 확장성, 완전한 관리형 Authoritative DNS
> Authoritative = the customer (you) can update the DNS records

Domain Registrar

리소스에 대한 헬스체크 가능

AWS서비스에 대해서만 100% SLA제공

## Route 53 – Records

트래픽을 루팅하는 방식을 결정

레코드의 구성
- Domain/subdomain Name – e.g., example.com
- Record Type – e.g., A or AAAA
- Value – e.g., 12.34.56.78
- Routing Policy – how Route 53 responds to queries
- TTL – amount of time the record cached at DNS Resolvers

Route53 서포트 대상
- A /AAAA / CNAME / NS
- CAA/DS/MX/NAPTR/PTR/SOA/TXT/SPF/SRV

## Route 53 – RecordTypes
- A – maps a hostname to IPv4
- AAAA – maps a hostname to IPv6
- CNAME – maps a hostname to another hostname
    - The target is a domain name which must have an A or AAAA record
    - Can’t create a CNAME record for the top node of a DNS namespace (Zone Apex)
    - Example: you can’t create for example.com, but you can create for www.example.com
- NS – Name Servers for the Hosted Zone
    - Control how traffic is routed for a domain

## Route 53 – Hosted Zones
도메인 및 해당 하위 도메인으로 트래픽을 라우팅하는 방법을 정의하는 레코드용 컨테이너

- Public Hosted Zones : 인터넷(공개 도메인 이름)에서 트래픽을 라우팅하는 방법을 지정하는 레코드가 포함

- Private Hosted Zones : 하나 이상의 VPC(프라이빗 도메인 이름) 내에서 트래픽을 라우팅하는 방법을 지정하는 레코드를 포함

## Route 53 – Records TTL (Time To Live)
- High TTL – e.g., 24 hr
    
    비용이 적게드는 대신 레코드가 오래됨
- Low TTL – e.g., 60 sec.

    다소 비용이 발생하나, 레코드가 비교적 최신상태를 유지, 변경이 용이하다

> Alias 레코드를 제외한 모든 레코드는 TTL지정 필수

## CNAME vs Alias

- AWS 리소스(Load Balancer, CloudFront...)는 AWS 호스트 이름을 노출
    > lb1-1234.us-east-2.elb.amazonaws.com -> myapp.mydomain.com

- CNAME:
     - 호스트 이름이 다른 호스트 이름을 지정 (app.mydomain.com => blabla.anything.com) 
     - 루트 도메인이 아닌 경우에만 해당(일명 Something.mydomain.com)
- Alias:
    - 호스트 이름이 AWS 리소스를 지정(app.mydomain.com => blabla.amazonaws.com).
    - ROOT DOMAIN 및 NON ROOT DOMAIN(mydomain.com이라고도 함)에서 작동
    - 무료
    - 기본 상태 확인
    
## Route 53 – Alias Records
호스트 이름을 AWS 리소스에 매핑

- DNS 기능 확장
- 리소스의 IP 주소 변경을 자동으로 인식
- CNAME과 달리 DNS 네임스페이스(Zone Apex)의 최상위 노드에 사용가능(예: example.com)
- 별칭 레코드는 AWS 리소스(IPv4/IPv6)에 대해 항상 A 또는 AAAA 
- TTL 설정 불가

## Route 53 – Alias Records Targets
- Elastic Load Balancers
- CloudFront Distributions
- API Gateway
- Elastic Beanstalk environments
- S3 Websites
- VPC Interface Endpoints
- Global Accelerator accelerator
- Route 53 record in the same hosted zone
- EC2 DNS명 지정 불가


