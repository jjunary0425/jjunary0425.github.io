# EBS `Elastic Block Store`

EC2 인스턴스에 장착하여 사용할 수 있는 가상 저장 장치

## EBS가 필요한 경우
1. EC2가 제공하는 기본용량보다 더 사용해야 할 때
1. 운영체제를 중단시키지않고 자유롭게 용량을 늘리고 싶을 때
1. 영구적인 데이터 보관이 필요할 때
1. RAID등의 고급 기능이 필요할 때

## EBS 특징
- OS에서 일반적인 디스크 (HDD/SSD)처럼 인식
- 크기 성능(IOPS)자유롭게 설정
- 삭제전까지 데이터가 안전하게 유지

## EBS관련 용어
- 볼륨 `Volume` EBS의 가장 기본적인 형태로 OS에서 바로 사용가능한 상태

- Image `AMI` OS가 설치된 형태, EC2 인스턴스 바로 생성 가능
- SnapShot 
    - EBS볼륨의 특정 시점을 그대로 복사해 저장한 파일
    - 스냅샷을 이용하여 EBS볼륨과 AMI생성
- IOPS 저장 장치의 성능 추적 단위

## EBS 볼륨 포맷
- EC2 인스턴스에 장착된 EBS볼륨의 장치명을 확인
- EBS 볼륨 선택 후 세부내용에서 Attached Information 확인

- Attached Information에서 확인한 장치를 포맷
```
sudo mkfs -t ext4 /dev/sdf
```
## EC2인스턴스에 볼륨 마운트
- 리눅스에서 저장장치 사용을 위해 마운트 필요

```
sudo mount /dev/sdf /mnt
```
`/mnt 아닌 다른 디렉토리 지정 무방`

- 마운트된 저장장치 목록 확인
```
df -h
```

