{%hackmd theme-dark %}
# Azure Moodle install
###### tags: `Azure` `Moodle`
## 安裝套件

- 更新套件
```shell
sudo yum update
```

## 安裝apache

- 安裝Apache Server
```shell
sudo yum install httpd
```
- 設置開機啟用
```shell
sudo systemctl enable httpd
```
- 開啟Apache
```shell
sudo systemctl start httpd
```
## 安裝[php](https://www.itzgeek.com/how-tos/linux/centos-how-tos/how-to-install-php-7-3-on-rhel-8.html)
- 開啟Remi庫
```shell
sudo rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
```
```shell
sudo dnf install -y https://rpms.remirepo.net/enterprise/remi-release-8.rpm
``` 
- 列出可用PHP
```shell
sudo dnf module list php
```
- 啟用PHP
```shell
sudo dnf module enable php:remi-7.4 -y
```
- 安裝php
```shell
sudo dnf module enable php:remi-7.4 -y
```

## 安裝php擴展
```shell
sudo dnf install -y php-mysqlnd
```
```shell
sudo php -m | grep -i mysql
```
- 安裝 必要擴充
```shell
sudo yum install php-zip
```
```shell
sudo yum install php-gd php-init
```

## 安裝mairaDB
- 安裝
```shell
sudo yum install mariadb
```
- 開啟mairaDB
```shell
sudo systemctl start mariadb
```
- 設置開機啟動
```shell
sudo systemctl enable mariadb
```
### 創建資料庫
- 登入root
```shell
sudo mysql -u root -p
```
- 建立資料庫
```sql
create database moodle;
```
- 建立使用者及密碼
```sql
CREATE USER 'ksu'@'%' IDENTIFIED BY 'PASSWORD';
```
- 給予權限(PRIVILEGES)
```sql
GRANT ALL PRIVILEGES ON *.* TO 'ksu'@'%' IDENTIFIED BY 'PASSWORD';
```
- 刷新權限
```sql
FLUSH PRIVILEGES;
```
- 離開
```sql
exit;
```
## 安裝[moodle](https://download.moodle.org/download.php/direct/stable311/moodle-latest-311.tgz)
- 進入Apache目錄
```shell
cd /var/www/html
```
- 下載Moodle

1. wget
```shell
sudo wget https://download.moodle.org/download.php/direct/stable311/moodle-latest-311.tgz
```
```shell
sudo tar zxvf moodle-latest-311.tgz
``` 
2. git
```shell
sudo git clone https://github.com/moodle/moodle.git
```
- 建立moodle資料位置
```shell
sudo mkdir ../moodledata
```
- 給予權限
```shell
sudo chown -R apache:apache  ../html
```
```shell
sudo chown -R apache:apache ../moodledata
```
### 重新啟動
```shell
sudo systemctl restart httpd
```
