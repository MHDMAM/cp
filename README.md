
filebeat.prospectors:

# Each - is a prospector. Most options can be set at the prospector level, so
# you can use different prospectors for various configurations.
# Below are the prospector specific configurations.

- type: log

  # Change to true to enable this prospector configuration.
  enabled: false

  # Paths that should be crawled and fetched. Glob based paths.
  paths:
    #- /var/log/*.log
    #- c:\programdata\elasticsearch\logs\*
    - /home/path/logs/info/*
    - /home/path/logs/callback/*

  josn.keys_under_root: true

  processors:
    - decode_json_fields:
        fields: ["time", "level", "info", "path", "id", "source", "txnRefNo", "notificationType", "userDigitalId", "route", "body"]
        target: ""
        max_depth: 4


