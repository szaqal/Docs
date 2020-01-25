# Cheetsheet

## OPS

### BASH

```
for x in 52.32.30.222 34.211.88.188 52.32.135.222 22.164.194.22
do 
        ssh -i key.pem ubuntu@$x 'sudo apt-get -y install python'
done
```

### Rsync

Copy file over rsynch that allows resume

```
 rsync -P -rsh=ssh root@192.168.2.102:/mnt/file.gz ./file.sql.gz
```

### Mysql

```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

### TCPFLOW

```
tcpflow -c 
tcpflow -i eth1  port 8094 -C
```

### Generate file of arbitraty size

```
dd if=/dev/zero of=1g.img bs=1 count=0 seek=1G (1G)
dd if=/dev/zero of=test.img bs=1024 count=0 seek=$[1024*10] (10MB)
```

### Monitoring tools

dnstop and iftop
```
bash-4.4# apk add iftop dnstop
```

### List for older distributions  (ubuntu)

```
root@ubuntu-mesos-master:/etc/zookeeper/conf#  apt-cache madison docker-ce
 docker-ce | 5:18.09.0~3-0~ubuntu-xenial | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.06.1~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.06.0~ce~3-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
 docker-ce | 18.03.1~ce-0~ubuntu | https://download.docker.com/linux/ubuntu xenial/stable amd64 Packages
```

### GPG

```
gpg2 --batch --gen-key  ./keyData
gpg2 --list-keys
gpg2 --output  testfile_decrypt.txt --decrypt testfile.gpg
gpg2 --output  testfile.gpg --encrypt --recipient xxx@xxxx testfile.txt
gpg2 --armor --export xxx@xxxx
gpg2 --armor --export-secret-keys xxx@xxxx
```

### DUPLICITY

Create
```
duplicity --progress --encrypt-key=xxxx --encrypt-secret-keyring=/home/xxxx/.gnupg/trustdb.gpg   /home/xxxx/test/ file:///NAS/Backups/
```


## DEV

### Python

#### Install packages for python 3 if python 2 is default

```
python3 -m pip install yoyo-migrations
``` 
### Terminalizer 

Optimize GIF size from terminalizer

```
╰─$ convert demo.gif   -fuzz 20% -layers Optimize result.gif
```

### SDKMAN

```
sdk install java 8-oracle /Library/Java/JavaVirtualMachines/jdk1.8.0_201.jdk/Contents/Home
sdk default java 8-oracle
sdk list java
```

### AWS CLI

```
apt install awscli
```

```
AWS Access Key ID [None]: xxxxxxxxxxxxxxxxxxx 
AWS Secret Access Key [None]: xxxxxxxxxxxxxxxxxxx
Default region name [None]: us-west-2
Default output format [None]: json
```

```
aws s3 ls s3://some-logs/api/
aws s3 mv  s3://dir/ /local/path/s3/ --recursive
```

### GCloud

```
gcloud components list
gcloud components install pubsub-emulator
gcloud components update
gcloud beta emulators pubsub start
```

### Apache Ignite

```
./control.sh --activate
./sqlline.sh -u jdbc:ignite:thin://xxx.xxx.xxx.xxx
```

### Protobuffers

```
protoc -I service/ service/service.proto --go_out=plugins=grpc:service
```

