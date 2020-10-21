# Bash Cheetsheet

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