# observabilidade-elastic

Dar permissões aos volumes para permitir autorização de escrita.

`
sudo chown -R root:root
`

`docker run \
docker.elastic.co/beats/metricbeat:8.3.3 \
setup -E setup.kibana.host=172.17.210.54:5601 \
-E output.elasticsearch.hosts=["172.17.210.54:9200"]`

https://www.docker.elastic.co/


Inserir esse comando dentro do container do Elasticsearch
``


Inserir esse comando dentro do conteiner do Kibana
bin/kibana-verification-code

python manage.py elasticapm check
