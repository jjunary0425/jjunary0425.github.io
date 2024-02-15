# Access Key

엑세스 키 `Access Key`와 시크릿 키 `Secret Key`는 AWS API와 3rd party tool을 사용할 때 필요한 인증 수단

- API와 3rd party tool을 사용할 때 생성
- AWS의 모든 리소스는 API로 제어가 가능
- 엑세스 키와 시크릿 키 유출되지 않도록 주의
- AWS 에서는 IAM`Identity and Access Management`에서 계정을 생성한 뒤 권한을 제한할 것을 권장

![AccessKey](../images/AWS/AWS_ACCESS_KEY.png)

## aws cli 엑세스 키 설정

```
aws configure

```
동작 확인

```
aws iam list-users
```

결과

```
{
    "Users": [
        {
            "Path": "/",
            "UserName": "rimapa",
            "UserId": "AIDA3TCCCNUVN4ANEL2FH",
            "Arn": "arn:aws:iam::796855004458:user/rimapa",
            "CreateDate": "2023-12-21T06:35:10+00:00",
            "PasswordLastUsed": "2024-01-04T06:45:24+00:00"
        }
    ]
}
```