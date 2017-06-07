---
title: Workato connectors - Workday RaaS
date: 2017-06-06 06:38:00 Z
---

# Workday Report as a Service

## Custom Reports

Custom Reports (advanced type) can be exposed as a Web Service to be used programmatically. Workato uses this web service to automate report generation and to integrate report data from Workday to other applications.

### How to find JSON endpoint

Find URL in Actions > Web Service > View URLs

![View RaaS URL](/assets/images/workday/view_raas_url.png)

Right click `JSON` and choose "Copy URL"

![RaaS JSON URL](/assets/images/workday/copy_raas_json_url.png)

## Filter parameters

Prompts behave like request parameters. In the UI, it is presented as input fields before generating actual report. As a REST endpoint, these prompts are passed as request parameters.

### Report User Interface

![RaaS prompts](/assets/images/workday/raas_prompts.png)

JSON Example
https://wd2-impl-services1.workday.com/ccx/service/customreport2/workato/workato/Investors?format=json&Worker_Type!WID=d588c41a446c11de98360015c5e6daf6&Base_Pay=0

### Basic Setup

#### Report type

Switch to advanced type if not already. Only Advanced custom reports can be used in RaaS.

![RaaS prompts](/assets/images/workday/raas_change_to_advance.png)

#### Add prompts

Add all default prompts that are required of web-service-enabled reports. Add additional prompts as desired.

![RaaS prompts](/assets/images/workday/raas_add_prompts.png)

In this example, Base Pay is assigned to Prompt Qualifier as Prompt #1, which will be used in filters.

#### Add filters

Apply logic to filter prompt values
Use values from Prompt to compare against report column values. Example, assign Prompt parameter Base Pay as Prompt #1

![RaaS prompts](/assets/images/workday/raas_add_filter.png)

When generating a report, Base Pay parameter will be checked. If a value if provided, only records with Base Pay greater than the provided value will be included in the report.