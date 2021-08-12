## README
AmazonLinux2でJenkinsをインストールするPlayBook



### ansibleのインストール
```
# ワークディレクトリ
$ pwd
/home/ec2-user

# パッケージ最新化
$ sudo yum update -y

# インストール
$ sudo amazon-linux-extras install -y ansible2

# バージョン確認
$ ansible --version

```

### git clone 
```
$ git clone https://github.com/kotato-tohi/Jenkins_install.git
```

### hostsファイルの編集
```
[server]
<ターゲットノードのIPv4アドレス>

[server:vars]
ansible_ssh_port=22
ansible_ssh_user=ec2-user
ansible_ssh_private_key_file=<秘密鍵のパス>

```

### playbookの実行
```
$ ansible-playbool -i hosts playbook.yml 
```

### jenkinsにアクセス
http;//<IPアドレス>:8080