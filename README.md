# Getting started with the Elastic Stack and Docker-Compose

This repo is in reference to the blog [Getting started with the Elastic Stack and Docker-Compose](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose)

Please feel free to ask any questions via issues [here](https://github.com/elkninja/elastic-stack-docker-part-one/issues), our [Community Slack](https://ela.st/slack), or over in our [Discuss Forums](https://discuss.elastic.co/).

Pull Requests welcome :)

 docker cp es01:/usr/share/elasticsearch/config/certs/ca/ca.crt /tmp/.
 then restart conteinaer
 then


root@vmi1004282:~# docker restart $(docker ps -aq)

root@vmi1004282:~# curl --cacert /tmp/ca.crt -u elastic:changeme https://localhost:9200
curl: (35) OpenSSL SSL_connect: SSL_ERROR_SYSCALL in connection to localhost:9200 
root@vmi1004282:~# docker ps 
CONTAINER ID   IMAGE                                                 COMMAND                  CREATED         STATUS                             PORTS                              NAMES
2af7094bac81   docker.elastic.co/logstash/logstash:8.7.1             "/usr/local/bin/dock…"   3 minutes ago   Up 33 seconds                      5044/tcp, 9600/tcp                 logstash01
04b7ac50e9d8   docker.elastic.co/beats/filebeat:8.7.1                "/usr/bin/tini -- /u…"   3 minutes ago   Up 31 seconds                                                         filebeat01
51d62df337df   docker.elastic.co/kibana/kibana:8.7.1                 "/bin/tini -- /usr/l…"   3 minutes ago   Up 30 seconds (health: starting)   0.0.0.0:5601->5601/tcp             kibana
9b21a954102d   docker.elastic.co/elasticsearch/elasticsearch:8.7.1   "/bin/tini -- /usr/l…"   3 minutes ago   Up 30 seconds (health: starting)   0.0.0.0:9200->9200/tcp, 9300/tcp   es01
c87b3e38b05d   docker.elastic.co/elasticsearch/elasticsearch:8.7.1   "/bin/tini -- /usr/l…"   3 minutes ago   Up 29 seconds (healthy)            9200/tcp, 9300/tcp                 kibana-setup-1
root@vmi1004282:~# curl --cacert /tmp/ca.crt -u elastic:changeme https://localhost:9200


to remove containers and their volumes : 
docker-compose down -v 