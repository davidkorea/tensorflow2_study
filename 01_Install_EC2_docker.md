
# Install on EC2 docker


# 1. install docker on EC2

> [在 Amazon Linux 2 上安装 Docker](https://docs.aws.amazon.com/zh_cn/AmazonECS/latest/developerguide/docker-basics.html)

- `sudo yum update -y`
- `sudo yum install docker`
- `sudo service docker start`
- `sudo usermod -a -G docker ec2-user`
- `docker info`
