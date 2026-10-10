\# Домашнее задание к лекции 2 — Стенд мониторинга



\## Состав стенда



\### Стек 1: Telegraf + InfluxDB + Grafana

\- Плагины: CPU, RAM, Swap, Disk, Disk I/O, Network, Processes, Kernel, System

\- Интервал сбора метрик: `60s`

\- Порты: Grafana — 3000, InfluxDB — 8086, StatsD — 8125

\- Дашборд: Telegraf System Dashboard (grafana.com ID 928)



\### Стек 2: Node-exporter + Prometheus + Grafana

\- Интервал scrape: `36s`

\- Порты: Grafana — 3001, Prometheus — 9090, Node-exporter — 9100

\- Дашборд: Node Exporter Full (grafana.com ID 1860)



\## Запуск



\### Telegraf-стек

```bash

cd telegraf

docker compose up -d

```

\- Grafana: http://localhost:3000 (admin/admin)

\- InfluxDB: http://localhost:8086



\### Prometheus-стек

```bash

cd prometheus

docker compose up -d

```

\- Prometheus: http://localhost:9090

\- Node-exporter: http://localhost:9100/metrics

\- Grafana: http://localhost:3001 (admin/admin)



\## Скриншоты



\- `screenshots/telegraf-dashboard.png` — дашборд Telegraf, Last 15 minutes

\- `screenshots/prometheus-dashboard.png` — дашборд Node Exporter Full, Last 15 minutes

\- `screenshots/prometheus-targets.png` — targets в Prometheus (node UP)



\## Примечания



Стенд развёрнут через Docker Desktop на Windows 11. Node-exporter смонтирован с хоста (/proc, /sys, /) и отдаёт аппаратные метрики машины.

