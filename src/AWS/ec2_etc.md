# EC2 기타 설정 및 기능

## Placement Group
물리적으로 인접한 곳에 EC2인스턴스를 생성하여 네트워크 퍼포먼스를 극대화
- 100Gbps 네트워크 제공
- 인스턴스 생성시 설정 필요, 이미 생성된 인스턴스 포함 불가능
- 클러스터링, 고성능 컴퓨팅에 적합
- 추가요금 X

## Bundle Instance `Instance Store AMI`
인스턴스 스토리지를 Root장치로 사용하는 Windows EC2 인스턴스의 내용을 S3버킷에 저장하는 기능

[Windows Instance용 사용 설명서](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/WindowsGuide/concepts.html)

## Bundle Task
Bundle Instance 기능이 처리 되는 과정

## Network Interface 
ENI `Elastic Network Interface` 를 생성하고 EC2인스턴스에 장착

- EC2 인스턴스에 ENI를 여러개 장착할 수 있고, 장착 제거 유동적
- EC2 인스턴스가 속하지 않은 다른 VPC와 통신이 필요할때 사용
    - 공개망과 사설망을 함께 연결하고 싶은 경우
    - EC2 인스턴스에 대역폭이 다른 네트워크를 2개 가지고 싶은 경우 


