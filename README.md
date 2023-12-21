# 安装说明
## 测试系统
ubuntu20.04
## 环境
ansible >= 2.12

python >= 3.8
## 修改配置
### 添加 .vault-password.txt
```
rm -rf group_vars/secret.yml
openssl rand -base64 24 > .vault-password.txt
ansible-vault create group_vars/secret.yml
vault_id_secret: secret # CHANGE ME NOW!!!
```
### 修改管理员用户邮箱
![image](https://github.com/ywj0101/galaxy-install/assets/55040324/c1f39f61-94c0-4c67-9137-fa74dc0bf217)

### 修改 group_vars/galaxyservers.yml 文件的路径配置（非必要）
![image](https://github.com/ywj0101/galaxy-install/assets/55040324/ed3e5932-59d8-4b8f-8285-0574209fefd8)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/7daf47dd-6716-4163-b3f3-b3908ecd1d42)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/3af0daf4-d6df-4cef-9588-10aa6ff71765)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/4058d0aa-0bfb-4737-9335-077ae888cbdf)

### nginx 不开启ssl，代码中是不开启的（没有ssl证书，必须步骤）
![image](https://github.com/ywj0101/galaxy-install/assets/55040324/e3d6ce15-059f-4fba-ad7a-bd66c7d6c343)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/5f3f9350-0e88-41d5-a4ae-1725fdad2c6f)
## 执行脚本
```
# 安装roles
ansible-galaxy install -p roles -r requirements.yml
# 运行
ansible-playbook galaxy.yml
```
## 查看日志
### 查看galaxy运行日志
```
galaxyctl follow
```
### 查看nginx日志
```
journalctl -fu nginx
```

## 帮助文档
[step1](https://training.galaxyproject.org/training-material/topics/admin/tutorials/ansible-galaxy/tutorial.html#requirements)

[step4](https://training.galaxyproject.org/training-material/topics/admin/tutorials/tus/tutorial.html)

[step5](https://training.galaxyproject.org/training-material/topics/admin/tutorials/cvmfs/tutorial.html)

[step6](https://training.galaxyproject.org/training-material/topics/admin/tutorials/apptainer/tutorial.html)
