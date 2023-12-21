# IAM `Identity and Access Management`
AWS의 유저를 관리하는 Global service

- 기본적으로 생성된 루트 계정은 사용하거나 공유해서는 안 됩니다.
- 사용자는 조직 내의 사람들이며 그룹화될 수 있습니다.
- 그룹에는 사용자만 포함되며 다른 그룹은 포함되지 않습니다.
- 사용자는 반드시 그룹에 속할 필요는 없으며, 여러 그룹에 속할 수 있습니다.

## Permissions

- Users or Groups can be assigned JSON documents called policies
- These policies define the permissions of the users
- In AWS you apply the least privilege principle: don’t give more permissions than a user needs

- 사용자 또는 그룹에 정책이라는 JSON 문서를 할당할 수 있습니다.
- 이러한 정책은 사용자의 권한을 정의합니다.
- AWS에서는 최소 권한 원칙을 적용합니다. 즉, 사용자에게 필요한 것보다 더 많은 권한을 부여하지 마십시오.

```
{
    "Version": "2012-10-17", 
    "Statement": [
        {
            "Effect": "Allow", "Action": "ec2:Describe*", "Resource": "*"
        }, 
        {
            "Effect": "Allow",
            "Action": "elasticloadbalancing:Describe*", "Resource": "*"
        }, 
        {
            "Effect": "Allow",
            "Action": [
            "cloudwatch:ListMetrics", "cloudwatch:GetMetricStatistics", "cloudwatch:Describe*"
            ],
            "Resource": "*"
        }
    ]
}
```


### Policy은 다음으로 구성됩니다.
- Version: 정책 언어 버전, 항상 “2012-10- 17” 포함
- Id:정책에 대한 식별자(선택)
- Statement: 하나 이상의 개별 명세서(필수)

### 명령문은 다음으로 구성됩니다.
- Sid:문에 대한 식별자(선택)
- Effect: 문이 액세스를 허용하거나 거부하는지 여부(허용, 거부)
- Principal`주체`: 본 정책이 적용되는 계정/사용자/역할
- Action: 이 정책이 허용하는 작업 목록은 거부를 허용합니다.
- Resource: 작업이 적용된 리소스 목록
- Condition`조건`: 이 정책이 적용되는 조건(선택 사항)


![IAM](../../images/AWS/AWS_IAM.drawio.svg)