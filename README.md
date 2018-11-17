# Brostash Logstash pipeline

A collection of script and configurations for an ELK stack setup with Bro IDS logs as an input. The repository have the following structure:

* `./index_template`: Elasticsearch index template mapping for bro logs. To deploy running the following:

    ```
curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_template/bro -d @bro_template.json
    ```

* `./conf.d`: Logstash plugins scripts. The sub directory `bro_filters` contains a set of scripts for processing Bro IDS generated Logs. Among others, the `net flow`, `dns` and `http` logs are processed.

* `./pattern`: Grok patterns for the Logstash processing pipeline.
