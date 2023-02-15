# Cheetsheet

Ops Monitoring
---

dnstop, iftop,iperf


Mysql
---

```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

Network
---

```
tcpflow -i eth1  port 8094 -C
```

### APT through proxy

In /etc/apt/apt.conf
```
Acquire::http::Proxy "http://proxy:3128";
```


### Generate file of arbitraty size

```
dd if=/dev/zero of=1g.img bs=1 count=0 seek=1G (1G)
dd if=/dev/zero of=test.img bs=1024 count=0 seek=$[1024*10] (10MB)
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
Check encryption key id 
```
gpg2 --list-packets duplicity-full.20200125T095437Z.vol1.difftar.gpg 
gpg: encrypted with RSA key, ID FB0F52F6BA77FB4D
```


### DUPLICITY

Create
```
duplicity --progress --encrypt-key=xxxx --encrypt-secret-keyring=/home/xxxx/.gnupg/trustdb.gpg   /home/xxxx/test/ file:///NAS/Backups/
duplicity list-current-files file:///NAS/Backups
```
Restore
```
duplicity restore file:///opt/raid/Backups/ .
```


## DEV

### Python

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

### Memcached

```
stats slabs
stats cachedump 3 100

```
```
watch memcdump --servers=localhost
```




### Ansible 

#### Test connectivity

```
[root@localhost openshift-ansible]# ansible -i inventory/hosts.localhost all -m  ping 
localhost | SUCCESS => {
    "changed": false, 
    "ping": "pong"
}

```

### Ask for password instead of ssh auth + sudo w/o parssword

```
 ansible-playbook playbook.yml --sudo  --ask-pass --ask-sudo-pass
```



### Bash

#### Copy Keys

```
for x in 52.32.30.222 34.211.88.188 52.32.135.222 22.164.194.22
do 
        ssh -i key.pem ubuntu@$x 'sudo apt-get -y install python'
done
```

#### Check ignorecase

```
Z="${X,,}"
if [ "$Z" = "y" ]; then
    echo "YES"
```


### GO

#### Project

[GoReportCard ](https://github.com/gojp/goreportcard)

```
go build -ldflags "-X main.Build=$(git rev-parse --short HEAD)"
```

![goenv](goenv.gif)




### Hadoop 

#### HDFS health report

```
hdfs dfsadmin -report
```

#### Basic operrations 

```
hdfs dfs -ls /dataset/
hdfs dfs -put TrafficSpeeds.csv /dataset/
hdfs dfs -put Crimes.csv /dataset/
```

#### Import files with provided replication factor

```
 hdfs dfs -D dfs.replication=8 -put * /datasets/
```

#### Remove Recursive Dir

```
 hdfs dfs -rmr /tmp/tpcds-generate
```
#### List jobs

```
hadoop job -list
```
