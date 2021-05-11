# ElasticSearch 6.8 docker image

Built by backporting the 7.12 ARM64 Dockerfile and copying the JDK from the 7.12 ElasticSearch docker distribution for ARM 64 to the 6.8 ElasticSearch distribution in this repo (elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz)

# Building the image
```
docker build . -t elyalvarado/elasticsearch:6.8
```

# Running the image
To run it:

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" elyalvarado/elasticsearch:6.8
```
