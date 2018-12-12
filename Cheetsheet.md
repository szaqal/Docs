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
