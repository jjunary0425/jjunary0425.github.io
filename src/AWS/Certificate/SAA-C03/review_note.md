# SAA-C03 오답 노트
AWS Certified Solutions Architect - Associate

[자격증 정보](https://aws.amazon.com/ko/certification/certified-solutions-architect-associate/?nc1=h_ls)

## IAM

<font size = 4, color = red>IAM 사용자 그룹은 다른 사용자 그룹에 속할 수 X </font>

<font size = 4, color = red>IAM 정책의 문장`statement`은 시드`sid`, 효과`effect`, 원칙`principal`, 조치`action`, 리소스`resource`, 그리고 조건`condition`으로 구성</font> <br> 버전`version`은 IAM 정책`policy` 자체의 일부이지, 문장`statement`의 일부가 X

## EC2 기초

온프레미스 애플리케이션을 AWS로 이전하려 합니다. 여러분의 기업에는 애플리케이션을 전용 서버에서 실행해야 한다는 엄격한 규정이 있습니다. 또한 비용 절감을 위해 전용 서버 바운드 소프트웨어 라이선스를 사용해야 합니다. 이 경우, 다음 중 어떤 EC2 구매 옵션이 적합할까요

> 전용 호스트

데이터베이스 기술을 EC2 인스턴스에 배포하려 합니다. 공급 업체 라이선스는 물리적 코어 및 기반 네크워크 소켓 가시성를 기반으로 비용을 책정합니다. 이 경우, 어떤 EC2 구매 옵션을 사용해야 가시성을 확보할 수 있을까요?

> 전용 호스트 


EC2 절전 모드를 활성화하기 위해서는 EC2 인스턴스 루트 볼륨 유형이 EBS 볼륨이어야만 하며, 민감한 내용을 보호할 수 있도록 암호화되어야 한다