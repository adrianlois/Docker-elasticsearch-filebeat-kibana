# Docker - Elastic Stack: Elasticsearch, Filebeat y Kibana

Ejemplo del envío de logs de Apache2 a través de Filebeat desde la máquina cliente al Elasticsearch de la máquina servidor y visualizarlos en Kibana.

## Servidor

Máquina que recibe los logs de las máquinas clientes.

Iniciar los tres contenedores con docker-compose: **Elasticsearch, Filebeat y Kibana**
```
docker-compose up -d
```

## Cliente

Máquina que envía los logs de los servicios que estén parametrizados en Filebeat.

Instalar Filebeat
```
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.0.1-linux-x86_64.tar.gz
tar xzvf filebeat-7.0.1-linux-x86_64.tar.gz
```

- Parametrizar las opciones del fichero "/etc/filebeat/filebeat.yml" para el envío de logs de la máquina cliente al Elasticsearch de la máquina servidor.

- Opción para ejecutar Filebeat en la máquina cliente en modo contenedor con Docker: https://www.elastic.co/guide/en/beats/filebeat/current/running-on-docker.html
