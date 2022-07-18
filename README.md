# ElasticSearch 6.8 docker image

Built by backporting the 7.12 ARM64 Dockerfile and copying the JDK from the 7.12 ElasticSearch docker distribution for ARM 64 to the 6.8 ElasticSearch distribution in this repo (elasticsearch-6.8.16-SNAPSHOT-linux-aarch64.tar.gz)

# Building the image
```
docker build . -t elasticsearch-arm:6.8
```

# Get image from Github Registry
```
docker pull ghcr.io/baladins/elasticsearch-docker-arm64:6.8.24
docker tag ghcr.io/baladins/elasticsearch-docker-arm64:6.8.24 elasticsearch-arm:6.8
```

# Running the image
To run it:

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" elasticsearch-arm:6.8
```

# Publish the image to Github Registry
```
docker tag elasticsearch-arm:6.8 ghcr.io/Baladins/elasticsearch-arm:6.8
echo $GITHUB_TOKEN | docker login ghcr.io -u $USERNAME --password-stdin
docker push ghcr.io/baladins/elasticsearch-docker-arm64:6.8
```

# Publish the image to AWS Registry
```
docker tag elasticsearch-arm:6.8 public.ecr.aws/c2m6n8k8/elasticsearch-arm:6.8
aws ecr-public get-login-password --region=us-east-1 | docker login --username AWS --password-stdin public.ecr.aws
docker push public.ecr.aws/c2m6n8k8/elasticsearch-arm:6.8
```
