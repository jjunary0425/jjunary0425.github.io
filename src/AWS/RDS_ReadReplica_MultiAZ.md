# Read Replica & Multi AZ

## 읽기 성능 향상을 위한 Read Replica

- 최대 15개 까지 확장
- Within AZ, Cross AZ, Cross Region
- 비동기 복제를 하기때문에 일관성 유지 가능
- 마스터 디비로 승격 가능
- apllication에서 read replica를 마스터로 사용 할때는 연결 스트링을 갱신해야함
- 다른 리전에 replica를 둘 경우 네크워크 비용이 발생한다

## 재해 복구를 위한 Multi AZ

- 동기식 복제
- 장애 발생시 슬레이브 디비가 자동으로 승격

## 싱글 AZ -> Multi AZ
- 제로 다운타임
- 사용자는 수정을 클릭하기만 하면 됨
- 스냅샷 생성 -> 새로운 AZ에 디비 생성후 리스토어 -> 동기화 