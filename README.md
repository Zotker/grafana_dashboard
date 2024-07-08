# Дашборд мониторинга
Дашборд для мониторинга ресурсов сервера базы данных. 

![example](https://github.com/Zotker/grafana_dashboard/assets/108451609/b5bc6312-7fad-459c-9a10-3dc0b1b72ddb)

Преднеазначен для доставки данных в grafana из prometheus.

В данном дашборде используется node_exporter, postgres_exporter + кастомные запросы.

При добавлении новых экспортеров в prometheus необходимо для postgres_exporter'a добавить label **instance** с **_db** на конце.

Например:
```
  - job_name: "postgres_exporter"
    scrape_interval: 60s
    scrape_timeout: 10s
    static_configs:
      - targets: ['XXX.XXX.XXX.XXX:YYYY']
        labels:
          instance: 'server1_db'
```
