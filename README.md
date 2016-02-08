This is the OpenWeatherMap exporter for Prometheus.

It exposes weather metrics to the pushgateway.

A minimal `openweathermap_exporter.yml` would look like:

````
api_key: <yourkey>
cities:
  - Munich
  - Ulaanbaatar
  - Isachsen
````
