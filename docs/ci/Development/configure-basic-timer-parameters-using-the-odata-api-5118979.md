<!-- loio511897995c804a2b80a9c119468ab66c -->

# Configure Basic Timer Parameters Using the OData API

You can configure the **Timer** \(basic version\) flow step of an integration flow using the OData API.

> ### Note:  
> The configurations via OData API are supported for the Timer version 1.4 and above.



## Context

When you configure the timer using the configuration API, the topic explains the values ParameterKey can have . For details about API, see [Manage and query integration artifacts of design time and runtime](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fapi.sap.com%2Fapi%2FIntegrationContent%2Fresource%2FConfigurations_of_Integration_Flow).

> ### Remember:  
> When using the OData API to retrieve or update configuration, the response reflects the configurations for All option not those of a specific runtime profile. If you need to view or modify values at the runtime profile level, use the UI instead. See [Configure Externalized Parameters of an Integration Flow](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/configure-externalized-parameters-of-integration-flow?version=CLOUD&ai=true)



<a name="loio511897995c804a2b80a9c119468ab66c__timer_settings_and_parameters"/>

## Basic Timer Settings and Corresponding Parameters

The following table shows how the settings in the Timer UI are represented in the OData API.

****


<table>
<tr>
<th valign="top">

Field or UI Element

</th>
<th valign="top">

OData API Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Schedule: On Deployment

</td>
<td valign="top">

`simple.repeat=NONE`

</td>
<td valign="top">

Runs the integration flow once when it is deployed.

</td>
</tr>
<tr>
<td valign="top">

Schedule: On Day

</td>
<td valign="top">

`simple.repeat=NONE --simple.runOn=<date-time>`

</td>
<td valign="top">

Runs the integration flow once at the specified date and time.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Seconds

</td>
<td valign="top">

`simple.repeat=SECONDS`

</td>
<td valign="top">

Sets the repeat interval to seconds. Use `simple.every` to specify the number of seconds.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Minutes

</td>
<td valign="top">

`simple.repeat=MINUTES`

</td>
<td valign="top">

Sets the repeat interval to minutes. Use `simple.every` to specify the number of minutes.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Hourly

</td>
<td valign="top">

`simple.repeat=HOURS`

</td>
<td valign="top">

Sets the repeat interval to hours. Use `simple.every` to specify the number of hours.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Daily

</td>
<td valign="top">

`simple.repeat=DAYS`

</td>
<td valign="top">

Sets the repeat interval to days. Use `simple.every` to specify the number of days.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Weekly

</td>
<td valign="top">

`simple.repeat=WEEKS`

</td>
<td valign="top">

Sets the repeat interval to weeks. Use `simple.every` to specify the number of weeks.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Monthly

</td>
<td valign="top">

`simple.repeat=MONTHS`

</td>
<td valign="top">

Sets the repeat interval to months. Use `simple.every` to specify the number of months.

</td>
</tr>
<tr>
<td valign="top">

Repeat: Yearly

</td>
<td valign="top">

`simple.repeat=YEARS`

</td>
<td valign="top">

Sets the repeat interval to years. Use `simple.every` to specify the number of years.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

`simple.every=<number>`

</td>
<td valign="top">

Specifies the number of units between each execution based on the selected *Repeat* interval.

</td>
</tr>
<tr>
<td valign="top">

Days of Week

</td>
<td valign="top">

`simple.daysOfWeek=<day1>,<day2>,...` 

</td>
<td valign="top">

Specifies the days of the week on which the integration flow runs. Supported values are `MON`, `TUE`, `WED`, `THU`, `FRI`, `SAT`, and `SUN`.

</td>
</tr>
<tr>
<td valign="top">

Run On

</td>
<td valign="top">

`simple.runOn=<date-time>` 

</td>
<td valign="top">

Specifies the date and time at which the integration flow runs. Use with `simple.repeat=NONE` for a one-time schedule.

To configure the timer to run on a specific date and time, use `simple.repeat=NONE` together with `simple.runOn`. For example:

```
simple.repeat=NONE --simple.runOn=2026-10-01T09:00:00 --tz=Etc/GMT
```



</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

`--tz=<time-zone>`

> ### Remember:  
> This parameter is optional only in the case of `simple.repeat=NONE without --simple.runOn`as this represents a pure "**run on deployment**" schedule.



</td>
<td valign="top">

Specifies the time zone used for the schedule. The time zone identifier is displayed in parentheses in the Time Zone drop down.

For Example: If you select **\(UTC -08:00\) Pacific Standard Time \(US/Pacific\)** from the **Time Zone** drop down, the value in parentheses, `US/Pacific`, is the time zone identifier.

</td>
</tr>
<tr>
<td valign="top">

Start At

</td>
<td valign="top">

`--startAt=<date-time>`

</td>
<td valign="top">

Specifies the date and time from which the schedule starts running.

-   The format for date is

    `YYYY-MM-DD`

-   The format for time is

    `Hour:Minute:Seconds`

    Example: `09:18:50`




</td>
</tr>
<tr>
<td valign="top">

End At

</td>
<td valign="top">

`--endAt=<date-time>` 

</td>
<td valign="top">

Specifies the date and time after which the schedule stops running.

For example:

```
simple.repeat=DAYS --simple.every=1 --tz=IST --startAt=2026-09-10T08:00:00 --endAt=2026-12-31T08:00:00
```



</td>
</tr>
<tr>
<td valign="top">

Enter As: Multiple Schedule

</td>
<td valign="top">

`multiple.schedules=[<date-time1>,<date-time2>,...]`

</td>
<td valign="top">

Specifies multiple specific dates and times at which the integration flow runs.

</td>
</tr>
</table>



<a name="loio511897995c804a2b80a9c119468ab66c__parameter_syntax"/>

## Example Combining Multiple Parameters

-   **Simple Schedule**: The timer configuration is specified in the `ParameterValue` property. You can combine multiple parameters to create a schedule.

    For example, to run an integration flow every two hours in the GMT time zone:

    ```
    {
      "ParameterValue": "simple.repeat=HOURS --simple.every=2 --tz=Etc/GMT",
      "DataType": "custom:schedule"
    }
    ```

    This configuration runs the integration flow every two hours in the specified time zone.

-   **Multiple Schedules**:
    -   To configure specific date and time entries, use `multiple.schedules`.

        For example:

        ```
        multiple.schedules=[2026-10-01T10:00:00,2026-10-02T10:00:00] --tz=Etc/GMT
        ```

    -   To run an integration flow at two specific dates and times, use `multiple.schedules`.

        For example:

        ```
        {
          "ParameterValue": "multiple.schedules=[2026-10-01T10:00:00,2026-10-02T10:00:00] --tz=Etc/GMT",
          "DataType": "custom:schedule"
        }
        ```





<a name="loio511897995c804a2b80a9c119468ab66c__example_configurations"/>

## Example Configurations

The following examples show common timer configurations.

**Common Timer Configurations**


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

ParameterValue

</th>
</tr>
<tr>
<td valign="top">

Run once when the integration flow is deployed and timezone is GMT

</td>
<td valign="top">

`simple.repeat=NONE --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run once on a specific date and time in GMT timezone

</td>
<td valign="top">

`simple.repeat=NONE --simple.runOn=2026-10-01T09:00:00 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every 30 seconds

</td>
<td valign="top">

`simple.repeat=SECONDS --simple.every=30 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every 15 minutes

</td>
<td valign="top">

`simple.repeat=MINUTES --simple.every=15 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every 2 hours

</td>
<td valign="top">

`simple.repeat=HOURS --simple.every=2 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every day in UTC timezone

</td>
<td valign="top">

`simple.repeat=DAYS --simple.every=1 --tz=UTC`

</td>
</tr>
<tr>
<td valign="top">

Run every week on Monday and Friday in GMT timezone

</td>
<td valign="top">

`simple.repeat=WEEKS --simple.every=1 --simple.daysOfWeek=MON,FRI --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every month in GMT timezone

</td>
<td valign="top">

`simple.repeat=MONTHS --simple.every=1 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run every year in GMT timezone

</td>
<td valign="top">

`simple.repeat=YEARS --simple.every=1 --tz=Etc/GMT`

</td>
</tr>
<tr>
<td valign="top">

Run at multiple specific dates and times

</td>
<td valign="top">

`multiple.schedules=[2026-10-01T10:00:00,2026-10-02T10:00:00]`

</td>
</tr>
</table>



## Example for GET and PUT Operation



### **GET**

**Request**

```
GET https://<host>/api/v1/IntegrationDesigntimeArtifacts(Id='<ArtifactId>',Version='active')/Configurations
```

**Response**

```
{
  "d": {
    "results": [
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('timer')",
          "uri": "https://<host>:443/api/v1/Configurations('timer')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "timer",
        "ParameterValue": "simple.repeat=HOURS --simple.every=1 --tz=Etc/GMT",
        "DataType": "custom:schedule",
        "Description": null
      },
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('yashvirTimer')",
          "uri": "https://<host>:443/api/v1/Configurations('yashvirTimer')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "yashvirTimer",
        "ParameterValue": "simple.repeat=NONE --tz=Indian/Chagos",
        "DataType": "custom:schedule",
        "Description": null
      },
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('extTimer')",
          "uri": "https://<host>:443/api/v1/Configurations('extTimer')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "extTimer",
        "ParameterValue": "simple.repeat=NONE --tz=Indian/Chagos",
        "DataType": "custom:schedule",
        "Description": null
      },
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('advanced')",
          "uri": "https://<host>:443/api/v1/Configurations('advanced')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "advanced",
        "ParameterValue": "simple.repeat=NONE --tz=Etc/GMT",
        "DataType": "custom:schedule",
        "Description": null
      },
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('Test%20Value')",
          "uri": "https://<host>:443/api/v1/Configurations('Test%20Value')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "Test Value",
        "ParameterValue": "simple.repeat=NONE --tz=UTC",
        "DataType": "custom:schedule",
        "Description": null
      },
      {
        "__metadata": {
          "id": "https://<host>:443/api/v1/Configurations('SAP_ProfileId')",
          "uri": "https://<host>:443/api/v1/Configurations('SAP_ProfileId')",
          "type": "com.sap.hci.api.Configuration"
        },
        "ParameterKey": "SAP_ProfileId",
        "ParameterValue": "iflmap",
        "DataType": "xsd:string",
        "Description": null
      }
    ]
  }
}
```



### **PUT**

**Endpoint**

```
PUT https://<host>/api/v1/IntegrationDesigntimeArtifacts(Id='<ArtifactId>',Version='active')/$links/Configurations('<ParameterKey>')
```

**Request Headers**


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

`x-csrf-token`

</td>
<td valign="top">

Fetch token from a prior GET request and pass it here

</td>
</tr>
<tr>
<td valign="top">

`Content-Type`

</td>
<td valign="top">

`application/json`

</td>
</tr>
</table>

**Request Body**

```
{

"ParameterValue": "simple.repeat=HOURS --simple.every=2 --tz=Etc/GMT",

"DataType": "custom:schedule"

}
```

**Response**

A successful update returns HTTP `202 Accepted`. No response body is returned. Use a subsequent GET request to verify the updated value.

**Related Information**  


[Update and Validate Configuration Parameters](update-and-validate-configuration-parameters-2b92d3d.md "")

