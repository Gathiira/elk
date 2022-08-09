# ELK SETUP

To setup elastic search using docker compose and configure custom password

## CMDS

- `echo -e "ELASTIC_PASSWORD=mypassword123\nKIBANA_PASSWORD=mypassword123" > .env`

- `docker-compose up -d`

To access the service using django

```
ELASTIC_USERNAME = os.environ.get("ELASTIC_USERNAME", "elastic")
ELASTIC_PASSWORD = os.environ.get("ELASTIC_PASSWORD")

ELASTICSEARCH_DSL = {
    "default": {"hosts": f"{ELASTIC_USERNAME}:{ELASTIC_PASSWORD}@localhost:9200"},
}
```

If you want to configure KIBANA too, uncomment the configs in the docker compose
