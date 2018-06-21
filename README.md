--- 
filebeat.prospectors: 
  - 
    enabled: false
    josn.keys_under_root: true
    paths: 
      - /home/path/logs/info/*
      - /home/path/logs/callback/*
    processors: 
      - 
        decode_json_fields: 
          fields: 
            - time
            - level
            - info
            - path
            - id
            - source
            - txnRefNo
            - notificationType
            - userDigitalId
            - route
            - body
          max_depth: 4
          target: ""
    type: log
