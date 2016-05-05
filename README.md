This is the OpenWeatherMap exporter for Prometheus.

It exposes weather metrics to the pushgateway.

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
