# EC2 기타 설정 및 기능

## Placement Group
물리적으로 인접한 곳에 EC2인스턴스를 생성하여 네트워크 퍼포먼스를 극대화
- 100Gbps 네트워크 제공
- 인스턴스 생성시 설정 필요, 이미 생성된 인스턴스 포함 불가능
- 클러스터링, 고성능 컴퓨팅에 적합
- 추가요금 X

### Cluster

단일 가용 영역에서 인스턴스를 지연 시간이 짧은 그룹으로 클러스터링

사용 사례:
- 빠르게 완료해야 하는 빅데이터 작업
- 극도로 낮은 지연 시간과 높은 네트워크 처리량이 필요한 애플리케이션


### Spread 분산

기본 하드웨어 전체에 인스턴스를 분산(AZ당 최대 7개 인스턴스 그룹)

사용 사례:
- 고가용성을 극대화해야 하는 애플리케이션
- 각 인스턴스가 장애로부터 서로 격리되어야 하는 중요한 애플리케이션

### Partition 분할

AZ 내의 다양한 파티션(다양한 랙 세트에 의존)에 인스턴스를 확산시, 그룹당 EC2 인스턴스를 수백 개까지 확장(Hadoop, Cassandra, Kafka)

사용 사례: HDFS, HBase, Cassandra, Kafka

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

- ENI의 속성
	- 기본 프라이빗 IPv4, 하나 이상의 보조 IPv4 
	- 프라이빗 IPv4당 탄력적 IP(IPv4) 1개
	- 공용 IPv4 1개
	- 하나 이상의 보안 그룹
	- MAC 주소
- ENI를 독립적으로 생성하고 장애 조치를 위해 EC2 인스턴스에 즉시 연결(이동)가능
- 특정 가용 영역(AZ)에 바인딩

> [참고 자료](https://aws.amazon.com/ko/blogs/aws/new-elastic-network-interfaces-in-the-virtual-private-cloud/)

## EC2 Hibernate

- EC2 최대 절전 모드 :
  - 인메모리(RAM) 상태가 유지
  - 인스턴스 부팅이 훨씬 빨라 (OS가 중지/다시 시작되지 X)
  - 내부적으로: RAM 상태가 루트 EBS 볼륨의 파일에 기록
  - 루트 EBS 볼륨은 암호화되어야

- 사용 사례:
  - 장기 실행 처리
  - RAM 상태 저장
  - 초기화에 시간이 걸리는 서비스

- 지원되는 인스턴스 제품군 – C3, C4, C5, I3, M3, M4, R3, R4,T2,T3, ...
- 인스턴스 RAM 크기 – 150GB 미만
- 베어메탈 인스턴스에는 지원되지 X
- AMI – Amazon Linux 2, Linux AMI, Ubuntu, RHEL, CentOS 및 Windows... 
- 루트 볼륨 – EBS여야 하며 암호화되어 있어야 하며 인스턴스 스토어가 아니어야 하며 대용량이어야 
- 온디맨드, 예약 및 스팟 인스턴스에 사용 가능 
- 인스턴스는 60일 이상 절전 모드 X
