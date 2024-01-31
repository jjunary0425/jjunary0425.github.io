# AutoScaling

트래픽이 늘어나면 자동으로 EC2인스턴스를 생성해 서비스를 확장하는 기능

클라우드 서비스이기에 가능한 AWS의 대표적인 기능

보통 AutoScaling은 ELB와 함께사용
<br>생성한 인스턴스를 ELB에 연결하고 로드밸런싱 실시

Cloud Watch와 연동하여 CPU, 네트워크 사용이 늘어나거나 줄어들었으때 확장, 삭제 대응
<br>cloud watch 의 모든 측정치와 연동 가능

EC2 생성은 AMI를 이용 
<br>AMI 생성시 유저 데이터의 스크립트를 이용하여 깃에서 어플리케이션 기동

![ASG](../../images/AWS/AWS_Autoscale.drawio.svg)

## Auto Scaling 그룹 – 동적 조정 정책
- TargetTracking 스케일링
    - 가장 간단하고 설치가 용이함
    - 예: 평균 ASG CPU를 약 40%로 유지
- 단순/단계적 스케일링
    - CloudWatch 경보가 트리거되면(예: CPU > 70%) 장치 2개를 추가 
    - CloudWatch 경보가 트리거되면(예: CPU < 30%) 장치 1개를 제거
- 예약된 작업
    - 알려진 사용 패턴을 기반으로 확장을 예측
    - 예: 금요일 오후 5시에 인스턴스를 늘림
- 예측 확장: 지속적으로 로드를 예측하고 사전 확장을 예약