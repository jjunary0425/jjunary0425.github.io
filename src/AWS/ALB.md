# Application Load Balancer

애플리케이션 로드 밸런서는 레이어 7(HTTP)
- 시스템 전체(대상 그룹)에 걸쳐 여러 HTTP 애플리케이션에 대한 로드 밸런싱
- 동일한 시스템의 여러 애플리케이션에 대한 로드 밸런싱(예: 컨테이너)
- HTTP/2 및 WebSocket 지원
- 리디렉션 지원(예: HTTP에서 HTTPS로)

## Target Groups

- EC2 인스턴스(Auto Scaling 그룹에서 관리 가능) – HTTP 
- ECS 작업(ECS 자체에서 관리) – HTTP
- Lambda 함수 – HTTP 요청이 JSON 이벤트로 변환
- IP 주소 – 프라이빗 IP

- ALB는 여러 대상 그룹으로 라우팅 가능
- 상태 점검은 대상 그룹 수준에서 수행

## etc

- 고정 호스트 이름(XXX.region.elb.amazonaws.com)
- 애플리케이션 서버는 클라이언트의 IP를 참조 불가
- 클라이언트의 실제 IP가 X-Forwarded-For 헤더에 삽입
- 포트(X-Forwarded-Port) 및 프로토(X-Forwarded-Proto) 취득 가능