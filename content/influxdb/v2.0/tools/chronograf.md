---
title: Use Chronograf with InfluxDB OSS
description: >
  [Chronograf](/{{< latest "chronograf" >}}/) is a data visualization and dashboarding
  tool designed to visualize data in InfluxDB 1.x. It is part of the [TICKstack](/platform/)
  that provides an InfluxQL data explorer, Kapacitor integrations, and more.
  Continue to use Chronograf with **InfluxDB Cloud** and **InfluxDB OSS 2.0** and the
  [1.x compatibility API](/influxdb/v2.0/reference/api/influxdb-1x/).
menu:
  influxdb_2_0:
    name: Use Chronograf
    parent: Tools & integrations
weight: 103
related:
  - /{{< latest "chronograf" >}}/
---

[Chronograf](/{{< latest "chronograf" >}}/) is a data visualization and dashboarding
tool designed to visualize data in InfluxDB 1.x. It is part of the [TICKstack](/platform/)
that provides an InfluxQL data explorer, Kapacitor integrations, and more.
Continue to use Chronograf with **InfluxDB Cloud** and **InfluxDB OSS 2.0** and the
[1.x compatibility API](/influxdb/v2.0/reference/api/influxdb-1x/).

{{% warn %}}
### No administrative functionality
Chronograf cannot be used for administrative tasks in InfluxDB Cloud and InfluxDB OSS 2.0.
For example, you **cannot** do the following:

- Define databases
- Modify retention policies
- Add users

To complete administrative tasks, use the following:

- **InfluxDB user interface (UI)**
- [InfluxDB CLI](/influxdb/v2.0/reference/cli/influx/)
- [InfluxDB v2 API](/influxdb/v2.0/reference/api/)

### Limited InfluxQL support
InfluxDB Cloud and InfluxDB OSS 2.0 support InfluxQL **read-only** queries.
For more information, see [InfluxQL support](/influxdb/v2.0/query-data/influxql/#influxql-support).
{{% /warn %}}

## Create an InfluxDB connection
1. In Choronograf, click **Configuration** in the left navigation bar,
   and then click **{{< icon "plus" >}} Add Connection**.
2. Enter your InfluxDB connection credentials:
    - **Connection URL:** InfluxDB URL _(see [InfluxDB Cloud regions](/influxdb/cloud/reference/regions/)
      or [InfluxDB OSS URLs](/influxdb/v2.0/reference/urls/))_

      ```
      http://localhost:8086
      ```

    - **Connection Name:** Name to uniquely identify this connection configuration
    - **Username:** InfluxDB username
    - **Password:** InfluxDB [authentication token](/influxdb/v2.0/security/tokens/)
    - **Telegraf Database Name:** Default database name
    - **Default Retention Policy:** Default retention policy

    {{% note %}}
#### DBRPs map to InfluxDB buckets
In InfluxDB Cloud and InfluxDB OSS 2.0, database/retention-policy (DBRP) combinations
are mapped to buckets using the `database-name/retention-policy` naming convention.
For information, see [DBRP mapping](/influxdb/v2.0/reference/api/influxdb-1x/dbrp/)
and [Map unmapped buckets](/influxdb/v2.0/query-data/influxql/#map-unmapped-buckets).
    {{% /note %}}

3. Click **Add Connection**.
4. Select the dashboards you would like to create, and then click **Next**.
5. To configure a Kapacitor connection, provide the necessary credentials,
   and then click **Continue**. Otherwise, click **Skip**.
   _For information about using Kapacitor with InfluxDB Cloud or InfluxDB OSS 2.0,
   see [Use Kapacitor with InfluxDB](/influxdb/v2.0/tools/kapacitor/)._
6. Click **Finish**.
