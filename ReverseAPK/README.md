### apktool
```
docker run --rm -v `pwd`:/app theanam/apktool d apk_file.apk
```

### dex2jar
```
docker run --rm -v $(pwd):$(pwd) -w "$(pwd)" fspnetwork/dex2jar d2j-dex2jar.sh some.apk
```

### jadx
https://github.com/skylot/jadx/releases
