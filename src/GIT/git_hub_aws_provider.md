# Github actions에서 사용할 수 있는 AWS OIDC provider 구성





## AWS 접속 후 IAM 자격공급자 선택

![001](../../images/Git/OIDC_provider/001_iamprovider.png)

## 공급자추가 클릭
![002](../../images/Git/OIDC_provider/002_addprovider.png)

## 공급자 추가를 위한 정보 입력


> 입력내용은 [github guide](https://docs.github.com/ko/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services) 참조

- OpenID Connect
- 공급자 URL : https://token.actions.githubusercontent.com
- 지문가져오기

![003_01](../../images/Git/OIDC_provider/003_01.png)

- 대상 : sts.amazonaws.com

![003_02](../../images/Git/OIDC_provider/003_02.png)

- 공급자추가 클릭

![003_03](../../images/Git/OIDC_provider/003_03.png)

- 공급자가 추가된 것을 확인
![003_04](../../images/Git/OIDC_provider/003_04.png)