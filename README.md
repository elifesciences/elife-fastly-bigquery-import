# Fastly BigQuery Import
A set of functions, schemas and related information for taking Fastly logs stored on Google Cloud Storage and importing them into Google BigQuery

## Schema
The schema was obtained by importing the initial data into BigQuery using Google Dataprep and exporting the inferred schema:
```
bq show --format=prettyjson elife-fastly:production.generic_cdn | jq '.schema.fields'> schema.js
```
The schema format corresponds to the log format as set in builder terraform scripts here:
https://github.com/elifesciences/builder/blob/master/src/buildercore/terraform.py
