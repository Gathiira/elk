# ELK SETUP

To setup elastic search using docker compose and configure custom password

## CMDS

- `echo -e "ELASTIC_PASSWORD=mypassword123\nKIBANA_PASSWORD=mypassword123\nES_PORT=9201\nSTACK_VERSION=7.17.4" > .env`
- Be careful on elk version. It cuts accross all its dependencies.
- `docker-compose up -d`

To access the service using django

```
ELASTIC_USERNAME = os.environ.get("ELASTIC_USERNAME")
ELASTIC_PASSWORD = os.environ.get("ELASTIC_PASSWORD")
ELASTIC_HOST = os.environ.get("ELASTIC_HOST")
ES_PORT = os.environ.get("ES_PORT")

ELASTICSEARCH_DSL = {
    "default": {"hosts": f"{ELASTIC_USERNAME}:{ELASTIC_PASSWORD}@{ELASTIC_HOST}:{ES_PORT}"},
}

```

If you want to configure KIBANA too, uncomment the configs in the docker compose
