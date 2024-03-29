# AMI `Amazon Machine Images`

EC2 인스턴스를 생성하기 위한 기본 파일

- AWS에서는 빈 EC2 인스턴스에 직접 OS를 설치할 수 없기 때문에
- 미리 OS가 설치된 AMI를 이용하여 EC2 인스턴스를 생성
- AMI애는 OS뿐만 아니라 각종 Server Application, Database, Firewall 등 솔루션도 설치 가능
- 모든 설치와 설정이 완료된 AMI를 이용하여 EC2를 신속하게 늘릴 수 있기 때문에
- 자동 횡적 확장 `Auto Scaling` 가능

## AMI가 필요한 경우
- EC2 인스턴스를 신속하게 생성해야 할 때
- Auto Scaling등으로 자동화 할 때
- EC2 인스턴스를 다른 리전으로 이전해야 할 때
- 상용 솔루션을 사용하고자 할 때

## EC2 인스턴스로 AMI 생성
- Image name : AMI 이름
- Image description : AMI 설명
- No reboot : AMI를 생성할때 재부팅 없이 생성, 파일 시스템의 무결성 보장 X
- Instance Volume : 기본 장착될 EBS 볼륨

- AMI = Amazon 머신 이미지
- AMI는 EC2 인스턴스의 사용자 정의
- 자신만의 소프트웨어, 구성, 운영 체제, 모니터링을 추가 가능 
- 모든 소프트웨어가 사전 패키지되어 있으므로 부팅/구성 시간이 더 빨라진다
- AMI는 특정 지역용으로 구축(그리고 지역 간에 복사할 수 있음)
- 다음에서 EC2 인스턴스를 시작
  - 퍼블릭 AMI: AWS 제공
  - 자체 AMI: 직접 만들고 유지 관리
  - AWS Marketplace AMI: 다른 사람이 만든(및 잠재적으로 판매하는) AMI