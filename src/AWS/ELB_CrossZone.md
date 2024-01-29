# Cross Zone Load Balancing

교차 영역 로드 밸런싱:
각 로드 밸런서 인스턴스는 모든 AZ에 등록된 모든 인스턴스에 고르게 분산

- Application Load Balancer
    - Enabled by default (can be disabled at the Target Group level) 
    - No charges for inter AZ data
- Network Load Balancer & Gateway Load Balancer 
    - Disabled by default
    - You pay charges ($) for inter AZ data if enabled