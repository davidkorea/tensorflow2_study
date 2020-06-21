# tensorflow2_study

neraul network

- 国内aliyun pip源`https://mirrors.aliyun.com/pypi/simple/`, 使用国内源本机安装
  ```
  pip install -i https://mirrors.aliyun.com/pypi/simple --upgrade pip
  pip install -i https://mirrors.aliyun.com/pypi/simple tensorflow==2.2
  pip install -i https://mirrors.aliyun.com/pypi/simple jupyterlab
  ```
- `!apt-get install -y graphviz`, 在tensorflow官方容器中安装graphviz报错

  ```
  E: Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/libj/libjpeg-turbo/libjpeg-turbo8_1.5.2-0ubuntu5.18.04.3_amd64.deb  
    404  Not Found [IP: 91.189.88.152 80]
  E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
  ```
  - 解决方法 `!apt-get update --fix-missing && apt-get install -y graphviz `




