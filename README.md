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
`bin/elasticsearch-create-enrollment-token --scope kibana`

`./bin/elasticsearch-setup-passwords -u kibana_system auto
`


Inserir esse comando dentro do conteiner do Kibana
bin/kibana-verification-code

python manage.py elasticapm check


Password for the [elastic] user successfully reset.
New value: viT20EaBSHX_*cr4LCuV