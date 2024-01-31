# Load Balancer - SSL Certificates

로드밸런서는 X.509 인증서(SSL/TLS 서버 인증서)를 사용 
- ACM(AWS Certificate Manager)을 사용하여 인증서를 관리
- 대안으로 자신의 인증서를 업로드 가든
- HTTPS 리스너:
    - 기본 인증서를 지정해야 
    - 여러 도메인을 지원하기 위해 선택적 인증서 목록을 추가 가능
    - 클라이언트는 SNI(서버 이름 표시)를 사용하여 도달하는 호스트 이름을 지정가능
    - 이전 버전의 SSL/TLS(레거시 클라이언트)를 지원하는 보안 정책을 지정 기능

## Server Name Indication (SNI)

SNI는 여러 SSL 인증서를 하나의 웹 서버에 로드 다능
- 이는 "최신" 프로토콜이며 클라이언트가 초기 SSL 핸드셰이크에서 대상 서버의 호스트 이름을 나타내도록 요구
- 그러면 서버는 올바른 인증서를 찾거나 기본 인증서를 반환
- ALB 및 NLB(최신 세대), CloudFront에서만 작동


- Application Load Balancer (v2)
    - Supports multiple listeners with multiple SSL certificates 
    - Uses Server Name Indication (SNI) to make it work
- Network Load Balancer (v2)
    - Supports multiple listeners with multiple SSL certificates
    - Uses Server Name Indication (SNI) to make it work