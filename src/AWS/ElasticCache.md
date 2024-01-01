# Elastic Cache
분산 인 메모리 캐시 `In-Memory Cache`를 생성, 확장 가능한 서비스

Elastic Cache를 사용해야하는 이유 : 성능, 편의성, 분산 캐시 환경을 구축하는데 필요한 비용 절감

- 읽기 중심의 서비스를 제공해야하는 환경
- 고속으로 데이터를 분석해야하는 환경
- 자체 대용량 분산 캐시 운용이 부담스러울 때

전체 데이터는 일반적인 데이터베이스에 저장

자주 쓰이는 일부 데이터만 인 메모리 캐시에 저장

Elastic Cache는 두가지 엔진을 지원

- Memcached
- Redis

## Memcached
Elastic Cache를 이용하면 Memcached 클러스터를 손쉽게 생성, 확장 가능

Memcached 클러스터는 리전의 가용영역 `AZ`별로 생성 가능

노드를 추가하면 저장용량 증가

스냅샷, Read Replica 지원X

## Redis
클러스터 구성 X -> 노드 증가 X (용량 증가 X)

데이터를 저장하는 메모리 용량은 각 캐시 노드가 제공하는 메모리 용량에 한정

스냅샹, ReadReplica 지원

Failoveer 지원 : 마스터 노드 장애 발생시 ReadReplica가 마스터로 승격

ReadReplica는 리전의 여러 가용영역 `AZ`에 생성 가능

Redis캐시 노드가 제공하는 메모리 용량을 넘어서는 데이터를 저장하기 위해서는 애플리케이션 레벨에서 샤딩 구현 필요

## Elastci Cache 노드 유형
노드 : Elastic Cache의 인스턴스

노드 유형은 생성 후 변경 불가

| 노드 유형 | 설명 | 종류 |
| -- | -- | -- |
| 마이크로 | 가격이 가장 쌈, 낮은 vCPU성능과 213MB memory | cache.t1.micro |
| 표준 | 평균적인 vCPU, memory, network, I/O 용량을 제공 | cache.m1.small , cache.m1.medium , cache.m1.large |
| 고급형 | 표준보다 vCPU, memory가 많다 | cache.m3.xlarge , cache.m3.2xlarge |
| 고용량 메모리 | 고급형 보다 vCPU 작지만 훨씬 큰 메모리 제공, 높은 I/O 성능 |cache.m2.xlarge, cache.m2.2xlarge, cache.m2.4xlarge |
| 고성능 CPU | vCPU의 갯수와 성능이 높다 | cache.c1.large |

> [요금표](https://aws.amazon.com/ko/elasticache/pricing/)
