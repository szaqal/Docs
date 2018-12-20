# Cheetsheet

### RHEL

#### List RPM package files  

```
rpm -qpl xxx.x86_64.rpm
```

### Python

#### Install packages for python 3 if python 2 is default

```
python3 -m pip install yoyo-migrations
``` 

### GIT

#### Delete remote GIT tag

```
git push --delete origin v-xxxx-release
```

### BASH

```
for x in 52.32.30.222 34.211.88.188 52.32.135.222 22.164.194.22
do 
        ssh -i key.pem ubuntu@$x 'sudo apt-get -y install python'
done

```

### Docker

### List for older distributions  (ubuntu)

```
root@ubuntu-mesos-master:/etc/zookeeper/conf#  apt-cache madison docker-ce
 docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.06.1~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.06.0~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.03.1~ce-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
```

### Mysql

```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

### Rsync

Copy file over rsynch that allows resume

```
 rsync -P -rsh=ssh root@192.168.2.102:/mnt/file.gz ./file.sql.gz
```
