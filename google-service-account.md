---
layout: default
title: Google Service Account
nav_order: 3
permalink: /google-service-account
---

## Create a GCP Service Account to work with Achilio

To make Achilio work, you need to grant it access to your Google BigQuery project. This page explains how.

### Quick setup

The simplest way is to give the service account the 'Project Owner' role

```
SA_NAME=achilio-sa
gcloud iam service-accounts create ${SA_NAME} \
    --description="Service Account to use in Achilio" \
    --display-name="Achilio SA"
```

Then bind the Project Owner role to it

```
PROJECT=<your-project-here>

gcloud projects add-iam-policy-binding ${PROJECT} \
    --member="serviceAccount:${SA_NAME}@${PROJECT}.iam.gserviceaccount.com" \
    --role="roles/owner"
```

### Detailed Role

The list of minimum permissions required by Achilio to work is the following:

-   bigquery.jobs.listAll
-   bigquery.jobs.get
-   bigquery.jobs.list
-   bigquery.datasets.get
-   bigquery.tables.get
-   bigquery.tables.list
-   bigquery.tables.create
-   bigquery.tables.delete
-   resourcemanager.projects.get

To create a custom role using these permissions, run the following command:

```
PROJECT=<your-project>

gcloud iam roles create achilio --project=${PROJECT} --title=AchilioRole --description="Give the minimum required access to Achilio" --permissions=bigquery.jobs.listAll,bigquery.jobs.get,bigquery.jobs.list,bigquery.datasets.get,bigquery.tables.get,bigquery.tables.list,bigquery.tables.create,bigquery.tables.delete,resourcemanager.projects.get
```

Then bind it to the service account created earlier

```
SA_NAME=achilio-sa
PROJECT=<your-project>
gcloud projects add-iam-policy-binding ${PROJECT} \
    --member="serviceAccount:${SA_NAME}@${PROJECT}.iam.gserviceaccount.com" \
    --role="projects/achilio-dev/roles/achilio"
```
