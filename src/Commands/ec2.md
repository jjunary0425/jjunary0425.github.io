# My EC2 Commands

``` sh
[ec2-user@ip-172-31-40-52 ~]$ docker ps
[ec2-user@ip-172-31-40-52 ~]$ docker stop e44c25653cd9
e44c25653cd9
[ec2-user@ip-172-31-40-52 ~]$ docker ps
[ec2-user@ip-172-31-40-52 ~]$ docker images
[ec2-user@ip-172-31-40-52 ~]$  aws ecr get-login-password --region ap-northeast-1 | docker login --username AWS --password-stdin 796855004458.dkr.ecr.ap-northeast-1.amazonaws.com
Login Succeeded
[ec2-user@ip-172-31-40-52 ~]$ docker pull 796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst:latest
```


```

sudo yum install -y bind-utils

nslookup

dig
```
