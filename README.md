# 安装说明
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

### 修改 group_vars/galaxyservers.yml 文件的路径配置
![image](https://github.com/ywj0101/galaxy-install/assets/55040324/ed3e5932-59d8-4b8f-8285-0574209fefd8)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/7daf47dd-6716-4163-b3f3-b3908ecd1d42)

### nginx 不开启ssl，代码中是不开启的
![image](https://github.com/ywj0101/galaxy-install/assets/55040324/e3d6ce15-059f-4fba-ad7a-bd66c7d6c343)

![image](https://github.com/ywj0101/galaxy-install/assets/55040324/5f3f9350-0e88-41d5-a4ae-1725fdad2c6f)

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
