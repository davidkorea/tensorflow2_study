
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
```javascript
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
- `root@c0fb34a7929e:/# jupyter lab --config config.json `, 必须后缀json，否则报错
	```
	[I 07:31:24.903 LabApp] The Jupyter Notebook is running at:
	[I 07:31:24.903 LabApp] http://df0fa1736140:8888/
	[I 07:31:24.903 LabApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
	```
- access EC2 public ip:8888 
	- if install on local docker, access `127.0.0.1:8888`

<img width="600" src="https://user-images.githubusercontent.com/26485327/83982677-764f8200-a963-11ea-9a7c-57174a4c5696.png">




