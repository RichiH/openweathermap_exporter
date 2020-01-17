This is an [OpenWeatherMap](https://openweathermap.org/) exporter for [Prometheus](https://prometheus.io/).

It exposes weather metrics to the [pushgateway](https://github.com/prometheus/pushgateway).

A minimal `openweathermap_exporter.yml` would look like:

````
api_key: <yourkey>
cities:
  - Munich
  - Ulaanbaatar
  - Isachsen
latlons:
  - [40.2010176,-72.6806685]
zips:
  - 90210
````
Either `cities`, `lathlons` or `zips` can be provided.

Requirements:
 - Prometheus' Pushgateway installed and running on `localhost:9091`
 - Perl with packages `liblwp-useragent-determined-perl`, `libjson-perl` and `libconfig-yaml-perl`


An example `prometheus.yml` configuration looks like:

````
  - job_name: 'pushgateway'
    scrape_interval: 60s # Note this is NOT the interval the scripts will run; this is just the collection interval from the Pushgateway to Prometheus
    honor_labels: true
    static_configs:
      - targets: ['localhost:9091']
````
