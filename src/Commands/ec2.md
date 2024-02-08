# My EC2 Commands

``` sh
[ec2-user@ip-172-31-40-52 ~]$ docker ps
CONTAINER ID   IMAGE                                                                       COMMAND    CREATED       STATUS       PORTS                                       NAMES
e44c25653cd9   796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst:latest    "./main"   10 days ago   Up 10 days   0.0.0.0:3001->8080/tcp, :::3001->8080/tcp   cranky_northcutt
d1ff8ba0bc7c   796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/md-convertor-app:latest   "./main"   10 days ago   Up 10 days   0.0.0.0:3000->8080/tcp, :::3000->8080/tcp   eager_neumann
[ec2-user@ip-172-31-40-52 ~]$ docker stop e44c25653cd9
e44c25653cd9
[ec2-user@ip-172-31-40-52 ~]$ docker ps
CONTAINER ID   IMAGE                                                                       COMMAND    CREATED       STATUS       PORTS                                       NAMES
d1ff8ba0bc7c   796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/md-convertor-app:latest   "./main"   10 days ago   Up 10 days   0.0.0.0:3000->8080/tcp, :::3000->8080/tcp   eager_neumann
[ec2-user@ip-172-31-40-52 ~]$ docker images
REPOSITORY                                                           TAG       IMAGE ID       CREATED       SIZE
796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst    latest    da3dd879ebb1   10 days ago   1.22GB
796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/md-convertor-app   latest    4827efde32d4   2 weeks ago   1.18GB
[ec2-user@ip-172-31-40-52 ~]$  aws ecr get-login-password --region ap-northeast-1 | docker login --username AWS --password-stdin 796855004458.dkr.ecr.ap-northeast-1.amazonaws.com
WARNING! Your password will be stored unencrypted in /home/ec2-user/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
[ec2-user@ip-172-31-40-52 ~]$ docker pull 796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst:latest
latest: Pulling from my-coin-analyst
Digest: sha256:abafc6777876f0c36f545152246ce06ef3bcbf2a2516a081d6f15c8a5210ac6e
Status: Image is up to date for 796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst:latest
796855004458.dkr.ecr.ap-northeast-1.amazonaws.com/my-coin-analyst:latest
```