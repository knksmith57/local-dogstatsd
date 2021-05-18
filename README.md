# collect local [DogStatsD] metrics

> collect [DogStatsD] metrics on :8125/udp using [Telegraf], store to [InfluxDB], and visualize with [Chronograf]

## quickstart

```sh
$ git clone https://github.com/knksmith57/local-dogstatsd local-dogstatsd \
    && cd $_

$ docker-compose up -d

## open http://localhost:8888

$ echo -n "custom_metric:60|g|#shell:52" \
  | nc -4u -w0 localhost 8125
```

## cleanup

```sh
## temporarily stop collection but retain data for later
$ docker-compose stop

## destroy containers and collected data
$ docker-compose down --volumes
```

[dogstatsd]: https://docs.datadoghq.com/developers/dogstatsd/
[telegraf]: https://www.influxdata.com/time-series-platform/telegraf/
[influxdb]: https://www.influxdata.com/time-series-platform/
[chronograf]: https://www.influxdata.com/time-series-platform/chronograf/
