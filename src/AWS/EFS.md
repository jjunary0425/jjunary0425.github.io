# Amazon EFS `Elastic File System`

## Amazon EFS – 탄력적 파일 시스템
- 다수의 EC2에 탑재할 수 있는 관리형 NFS(네트워크 파일 시스템) 
- EFS는 다중 AZ의 EC2 인스턴스와 작동
- 고가용성, 확장성, 고가(3x gp2), 종량제 결제

- 사용 사례: 콘텐츠 관리, 웹 서비스, 데이터 공유, WordPress 
- NFSv4.1 프로토콜 사용
- 보안 그룹을 사용하여 EFS에 대한 액세스를 제어
- Linux 기반 AMI(Windows X)와 호환 가능
- KMS를 사용한 저장 암호화
- 표준 파일 API를 갖춘 POSIX 파일 시스템(~Linux)
- 파일 시스템은 자동으로 확장되고 종량제 요금이 부과되며 용량 계획이 불필요



## EFS 규모
  - 동시 NFS 클라이언트 1000대, 처리량 10GB 이상
  - 자동으로 페타바이트 규모의 네트워크 파일 시스템으로 확장
- Performance Mode (set at EFS creation time) 성능 모드(EFS 생성 시 설정)
  - General Purpose (default)  범용(기본값) – 대기 시간에 민감한 사용 사례(웹 서버, CMS 등...) 
  -  Max I/O 최대 I/O – 더 높은 대기 시간, 처리량, 고도의 병렬(빅 데이터, 미디어 처리)
- Throughput Mode 처리량 모드
  - Bursting 버스팅 – 1TB = 50MiB/s + 최대 100MiB/s의 버스트
  - Provisioned 프로비저닝됨 – 스토리지 크기에 관계없이 처리량을 설정 예: 1TB 스토리지의 경우 1GiB/s
  - Elastic 탄력성 – 워크로드에 따라 자동으로 처리량을 늘리거나 줄입
    - 읽기의 경우 최대 3GiB/s, 쓰기의 경우 1GiB/s 
    - 예측할 수 없는 워크로드에 사용됨

## Storage Tiers (수명 주기 관리 기능 – N일 후 파일 이동)
- Standard: 자주 액세스하는 파일용
- Infrequent Access(EFS-IA): 파일 검색 비용이 저렴하고 저장 비용이 저렴, 수명 주기 정책을 통해 EFS-IA 활성화

- 가용성 및 내구성
  - 표준: 다중 AZ, 프로덕션에 적합
  - One Zone: 개발에 적합한 하나의 AZ, 기본적으로 백업 활성화, IA와 호환(EFS One Zone-IA)

- 90% 이상의 비용 절감