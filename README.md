# observabilidade-elastic

Dar permissões aos volumes para permitir autorização de escrita.

`
sudo chown -R 1000:1000
`

`docker run \
docker.elastic.co/beats/metricbeat:8.3.3 \
setup -E setup.kibana.host=172.17.210.54:5601 \
-E output.elasticsearch.hosts=["172.17.210.54:9200"]`

https://www.docker.elastic.co/