# ELB Sticky session

동일한 클라이언트가 항상 로드 밸런서 뒤의 동일한 인스턴스로 리디렉션되도록 구현
- 이는 Classic Load Balancer, Application Load Balancer 및 Network Load Balancer에서 작동
- CLB 및 ALB 모두 stickiness에 사용되는 "쿠키"의 만료일은 귀하가 제어 가능
- 사용 사례: 사용자가 세션 데이터를 잃지 않도록 하는 경우
- 고정성을 활성화하면 백엔드 EC2 인스턴스에 대한 로드 불균형이 발생할 수

## Cookie Names
- 애플리케이션 기반 쿠키
	- Custom cookie
		- 대상에서 생성됨
		- 애플리케이션에 필요한 모든 사용자 정의 속성을 포함 가능
		- 쿠키 이름은 각 대상 그룹에 대해 개별적으로 지정되어야
		- AWSALB, AWSALBAPP 또는 AWSALBTG(ELB에서 사용하도록 예약됨)를 사용 X.
	- pplication cookie
		- 로드 밸런서에 의해 생성됨 
		- 쿠키 이름은:AWSALBAPP
- 기간 기반 쿠키
	- 로드 밸런서가 생성한 쿠키
	- 쿠키 이름:ALB의 경우 AWSALB, CLB의 경우 AWSELB
