# Elastic IP
고정 IP를 제공

공인 IP는 유동적 

DNS에 IP주소를 연결해 놓았는데 바뀌면 곤란하기 때문에 AWS에서 Elastic IP를 제공 (계정당 5개까지)

IPv4주소가 매우 부족하기 때문에 Elastic IP를 부여받고 EC2 인스턴스를 연결해야 요금이 부과 X

## Private vs Public IP 
- Public IP
  - 공용 IP는 인터넷(WWW)에서 해당 컴퓨터를 식별할 수 있음을 의미
  - 전체 웹에서 고유 (두 시스템이 동일한 공용 IP를 가질 수 없음). 
  - 지리적 위치를 쉽게 찾을 수 있음

- Private IP
  - 사설 IP는 사설 네트워크에서만 시스템을 식별할 수 있음
  - IP는 사설 네트워크 전체에서 고유
  - 두 개의 서로 다른 사설 네트워크(두 회사)가 동일한 IP를 가질 수 있음
  - 머신은 NAT + 인터넷 게이트웨이(프록시)를 사용하여 WWW에 연결
  - 특정 범위의 IP만 사설 IP로 사용할 수 있다.

## 공인 IP
- EC2 인스턴스를 생성하면 EC2 실행 중만 유효한 공인 IP가 부여
- EC2 인스턴스가 중단되면 IP주소를 반납
- EC2 인스턴스를 다시 시작하면 IP주소가 바뀔 수 `유동 IP`

## Elastic IP 사용 경우
- DNS 서버에서 도메인과 IP주소를 연결해야 할 때
- IP주소가 바뀌지 않고 계속 유지해야 할 때

## Elastic IP 연결하기
- Instance : EC2에 직접 연결할 경우 연결할 EC2 인스턴스
- Network Interface : ENI에 연결할 경유 연결할 Network Interface
- Private IP Address : 내부 IP 주소
- Reassociation : 해당 Elastic IP가 이미 다른곳에 연결되어 있는경우 에러가 발생, 강제로 연결 필요한 경우에만 설정