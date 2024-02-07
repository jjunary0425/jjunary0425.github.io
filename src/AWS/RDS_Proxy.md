# RDS Proxy

앱이 데이터베이스와 설정된 DB 연결을 풀링하고 공유할 수 있도록 허용

- 데이터베이스 리소스(예: CPU, RAM)에 대한 스트레스를 줄이고 열린 연결(및 시간 초과)을 최소화하여 데이터베이스 효율성향상
- Serverless, autoscaling, highly available (multi-AZ)
- RDS & Aurora failover time 을 66% 까지 절약 가능
- DB에 대한 IAM 인증을 시행하고 안전하게 AWS Secrets Manager에 자격 증명 저장
- RDS Proxy는 공개적으로 액세스 불가(VPC에서 액세스해야 함)