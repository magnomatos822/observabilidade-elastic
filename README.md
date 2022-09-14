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

`./bin/elasticsearch-setup-passwords -u kibana interactive`

Reset passwords in Elasticsearch
`./elasticsearch-reset-password  --interactive -u kibana`
`./elasticsearch-reset-password  --interactive -u kibana_system`

Criar Keystores
Criação do Keystore:

./bin/kibana-keystore create
Created Kibana keystore in /home/gsw.anselmoj/kibana-7.5.1-linux-x86_64/data/kibana.keystore

Adicionar a entrada do username (coloquei kibana):

./bin/kibana-keystore add elasticsearch.username
Enter value for elasticsearch.username: ******
Adicionando a entrada do password (coloquei a senha elastic):

./bin/kibana-keystore add elasticsearch.password
Enter value for elasticsearch.password: *******

Inserir esse comando dentro do conteiner do Kibana
bin/kibana-verification-code

python manage.py elasticapm check


Password for the [elastic] user successfully reset.
New value: viT20EaBSHX_*cr4LCuV


curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_cluster/settings -d '{ "transient": { "cluster.routing.allocation.disk.threshold_enabled": false } }'

curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_all/_settings -d '{"index.blocks.read_only_allow_delete": null}'

Modo 2
$curl -X PUT "http://[YOUR_ELASTICSEARCH_ENDPOINT]:9200/_cluster/settings?pretty" -H 'Content-Type: application/json' -d' { "transient": { "cluster.routing.allocation.disk.watermark.low": "50gb", "cluster.routing.allocation.disk.watermark.high": "20gb", "cluster.routing.allocation.disk.watermark.flood_stage": "10gb", "cluster.info.update.interval": "1m"}}'


curl -XPUT -H "Content-Type: application/json" http://172.17.210.54:9200/_cluster/settings -d '{ "transient": { "cluster.routing.allocation.disk.threshold_enabled": false } }'
curl -XPUT -H "Content-Type: application/json" http://172.17.210.54:9200/_all/_settings -d '{"index.blocks.read_only_allow_delete": null}'