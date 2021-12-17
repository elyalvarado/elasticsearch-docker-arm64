# ElasticSearch 6 docker image

# Building the image
```
docker build --no-cache -t elasticsearch:arm64-6.8.21 --build-arg ARCH=arm64v8 .
```

# Running the image
To run it:

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" elasticsearch:6.8.21
```
