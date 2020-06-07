
# Install on EC2 docker


# 0. EC2 SG

- 22
- 8888

# 1. Install docker on EC2

> [在 Amazon Linux 2 上安装 Docker](https://docs.aws.amazon.com/zh_cn/AmazonECS/latest/developerguide/docker-basics.html)

- `sudo yum update -y`
- `sudo yum install docker`
- `sudo service docker start`
- `sudo usermod -a -G docker ec2-user`
- `docker info`


# 2. Run tensorflow2.2.0 docker image

- `sudo docker run -itd -p 8888:8888  tensorflow/tensorflow:2.2.0`
- `sudo docker ps`, get docker container id c0fb34a7929e


# 3. Run jupyterlab in docker container

- jupyterlab config`touch config.json`
```
{
	"NotebookApp": {
		"ip": "*",
		"port": 8888,
		"password": "",
		"open_browser": false,
		"token": "",
		"allow_root": true
	}
}
```

- `sudo docker cp config.json c0fb34a7929e:/`
- `sudo docker exec -it c0fb34a7929e bash`
- `root@c0fb34a7929e:/# pip install jupyterlab`
- `root@c0fb34a7929e:/# jupyter lab --config config.json `

- access EC2 public ip:8888 






