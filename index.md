---
layout: default
title: Home
nav_order: 1
description: "Achilio Help center and documentation to help you manage your BigQuery with us."
permalink: /
---

<script>
  !function(){var analytics=window.analytics=window.analytics||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware"];analytics.factory=function(e){return function(){var t=Array.prototype.slice.call(arguments);t.unshift(e);analytics.push(t);return analytics}};for(var e=0;e<analytics.methods.length;e++){var key=analytics.methods[e];analytics[key]=analytics.factory(key)}analytics.load=function(key,e){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.src="https://cdn.segment.com/analytics.js/v1/" + key + "/analytics.min.js";var n=document.getElementsByTagName("script")[0];n.parentNode.insertBefore(t,n);analytics._loadOptions=e};analytics._writeKey="MNNlx43X9FU4JAC1tGMc89Rw99HvVcsQ";;analytics.SNIPPET_VERSION="4.15.3";
  analytics.load("MNNlx43X9FU4JAC1tGMc89Rw99HvVcsQ");
  analytics.page();
  }}();
</script>

<!-- # Home
Not working

## Table of contents

{: .no_toc .text-delta }

1. TOC
   {:toc} -->

# Welcome to Achilio documentation

Use Achilio to help you improve your productivity and quality of life as a Data engineer.

Achilio scans your query history to analyze your usage and give you insights, and make suggestions on how to improve its performances.

As of today, Achilio is a Materialized view suggestion tool. Materialized views are a powerful feature of Google BigQuery that should be leveraged correctly. We help you do that by suggesting the most relevant views that you could make depending on the usage on your warehouse.

## Quickstart

### Connect with your Google account

First connect to the Achilio app and login with your Organization Google account.

### Create a connection

-   Click on the connection tab on the nav bar, or on the hightlighted "create a connection" in the text above
-   Then on create your first connection to BigQuery
-   Give it a name, and copy paste the content of the json key of the service account you want to use for Achilio. [More info on service account permissions](google-service-account). Then click on 'Create Connection'

<!-- [Link](url) and ![Image](src) -->

### Register a project

Back to the home page, click "Register a new BigQuery project"

-   Type in the id (case-sensitive) of your project: for example, My First project id was "bamboo-volt-1234"
-   In the connection field, select the connection you created just earlier
-   Click "Synchronize with BigQuery"

### Synchronize your project and find your first Materialized views

Once you are on the Project Overview, you must start by synchronizing your warehouse with Achilio. This step will gather all you structures (dataset, table) as well as your query history. It does not fetch any data. If you want to make sure of that, you can [create a specific service account](google-service-account#detailed-role) with just the minimum necessary rights.

When this is done, you can click on "Find Materialized Views".

This can take a while, and then you can go to the "Materialized Views" tab to see what Achilio found.

### Review the suggested materialized views

Here you can review and accept, or discard, the materialized views suggested by the engine.

At first, a materialized view is in "proposal" state, and can be applied or discarded. If you click on "Apply", it will automatically create it on your warehouse.
If you click on "Discard" it will be simply removed. (If you click on "Find" again, the views you discarded will probably be suggested again unless you usage has changed between now and then).

When a View is created, you can remove it if you changed your mind. When removed, it will be deleted from you warehouse, but will still be suggested on Achilio. You have to then discard it if you really don't want it.

If you create some views that way, it may be that a "Find" at a latter time doesn't yield the same results, depending on how you usage evolved.
A view that you created and is not in the new proposal is flagged as "Outdated". You can decide if you want to keep it or not.

### Support or Contact

Having trouble with Achilio? You can contact the support at support@achilio.com and we will help you. You can also join our public Slack channel.
