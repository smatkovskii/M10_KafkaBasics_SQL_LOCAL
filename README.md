# Prerequisites

1. Docker and docker-compose
2. Bash-compatible environment such as WSL

# Executing the tutorial

Please follow [the guide](https://docs.confluent.io/platform/current/tutorials/examples/clickstream/docs/index.html) from Confluent portal. This README features screenshots for certain milestones of that guide.

## Startup step

You should see these 9 containers in Running state:
![](readme_assets/startup_containers.png)

> ⚠ It's possible that some of the containers will fail to start because of their interdependencies. In this case, run `docker-compose up -d` one more time.

## Create the Clickstream Data step

You should be able to sample all 3 datagen connectors:
![](readme_assets/ksqldb_print_clickstream.png)

## Verify the data step

You can inspect the created stream and tables and their dependencies via Confluent Center UI, `ksqlDB` -> `clickstream` -> `Flow` tab:
![](readme_assets/confluent_cc_tables_flow.png)

## Load the Clickstream Data in Grafana step

After completing the tutorial, you should be able to see Grafana dashboard with 6 metrics:
![](readme_assets/grafana_clickstream_dashboard.png)

# Metrics, detailed

## Users' IP addresses mapped to names and locations
![](readme_assets/grafana_clickstream_user_mappings.png)

## Sessionized user activity
![](readme_assets/grafana_clickstream_sessions.png)

## Enriched HTTP response codes statistics
![](readme_assets/grafana_clickstream_http_statuses.png)

## HTML pages requests per user
![](readme_assets/grafana_clickstream_html_pages.png)

## All events per user per minute
![](readme_assets/grafana_clickstream_events_per_user_per_minute.png)

## 400th HTTP errors per minute
![](readme_assets/grafana_clickstream_400th_errors.png)