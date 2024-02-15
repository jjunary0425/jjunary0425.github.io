# Routing Policies

Route 53이 DNS 쿼리에 응답하는 방법 정의
- '라우팅'이라는 단어를 혼동하지 마세요.
    - 트래픽을 라우팅하는 로드밸런서 라우팅과 동일하지 않습니다.
    - DNS는 트래픽을 라우팅하지 않고 DNS 쿼리에만 응답합니다.
- Route 53은 다음 라우팅 정책을 지원합니다.
    - 단순
    - 가중치 적용
    - 장애 조치
    - 지연 시간 기반
    - 위치정보
    - 다중값 답변
    - 지리 근접성(Route 53 트래픽 흐름 기능 사용)