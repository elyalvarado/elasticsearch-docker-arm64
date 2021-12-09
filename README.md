# ElasticSearch 6.4 docker image

# Building the image
```
docker build . -t elasticsearch:6.4.3 -t docker.elastic.co/elasticsearch/elasticsearch -t docker.elastic.co/elasticsearch/elasticsearch:6.4.3 
```

# Running the image
To run it:

```
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  -e "xpack.ml.enabled=false" elasticsearch:6.4.3
```
