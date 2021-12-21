### Matrix Synapse
> clone source
```
git clone https://github.com/ChouBetter/synapse.git
```
> move to /
```
mv synapse /.
```
> build image
```
docker build -t my/synapse -f docker/Dockerfile .
```
> init data
```
mkdir /data
```
> generate config
```
docker run -it --rm \
    -v /data:/data \
    -e SYNAPSE_SERVER_NAME=MY_SERVER_NAME \
    -e SYNAPSE_REPORT_STATS=yes \
    my/synapse:latest generate
```
> run server
```
docker run -d --name synapse \
    -v /data:/data \
    -p 8008:8008 \
    my/synapse:latest
```
