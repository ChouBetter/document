### Ubuntu
> Install Docker
```
apt-get install docker.io
```
> Install Docker-Compose
```
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
```
chmod +x /usr/local/bin/docker-compose
```
```
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
> Install Tools zip/unzip
```
apt-get install zip unzip
```

### CentOS
> Install Docker
```
yum install -y yum-utils
```
```
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
```
yum install docker-ce docker-ce-cli containerd.io
```
```
systemctl start docker
```
> Install Docker-Compose
```
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
```
chmod +x /usr/local/bin/docker-compose
```
```
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
> Install Tools zip/unzip
```
yum install zip unzip
```
