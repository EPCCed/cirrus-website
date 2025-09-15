---
layout: single
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---

&nbsp;

## Full system power down

Friday 29th August 2025  09:00 - Thursday 18th September 18:00

Due to a significant Health and Safety risk, associated with our power supply to the site, action is required at the Advanced Computing Facility (ACF). There will be a full power outage to the site during this period. Specialised external contractors will be working on a 24/7 basis for the outage period replacing switchgear. 

**Users will not be able to connect to Cirrus and will not be able to access data on any of the Cirrus file systems. The system will be drained of jobs ahead of the power outage and jobs will not run during this period. Any queued jobs will remain in the queue during the outage and jobs will start once the service is returned. SAFE and the Cirrus website will be available.**


----------


- [Current System Load](#current-system-load)
- [Known Issues](#known-issues)
- [Current Issues](#service-alerts)
- [Recent Issues](#recently-resolved-service-alerts)
- [Maintenance](#service-calendar-and-maintenance)
- [Cirrus service end](#cirrus-service-end)
- [Service Calendar and Maintenance](#service-calendar-and-maintenance)


## Current System Load

The plot below shows the status of the CPU nodes on the current Cirrus service for the past day
(note: the Cirrus GPU nodes are not included in this plot).

A description of each of the status types is provided below the plot.

### CPU

![Cirrus Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus.png)
{: style="width=80%" align="center"
alt="Cirrus Node Status over time" 
title="Cirrus Node Status over time"}

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 

### GPU
![Cirrus GPU Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus_gpu.png)
{: style="width=80%" align="center"
alt="Cirrus Node Status over time" 
title="Cirrus Node Status over time"}

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 



## Known Issues 

We are experiening a heavy load on the metadata server. Our systems team are investigating but we suspect this is due to user(s) performing many I/O operations. We apologise for the inconvenience this is causing users. 

## Service Alerts


{% assign current_alerts = site.alerts | where_exp: "alert", "alert.status == 'Ongoing'" %}
{% for alert in current_alerts reversed %}
    {% if forloop.first == true %}

  <table>
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>Scope</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>
    <tbody>
    {% endif %}
      <tr>
      <td>
        {{ alert.status }}
      </td>
      <td>
        {{ alert.type }}
      </td>
      <td>
        {{ alert.start_date | date: "%Y-%m-%d %H:%M" }}
      </td>
      <td>
        {{ alert.end_date | date: "%Y-%m-%d %H:%M" }}
      </td>
      <td>
        {{ alert.scope }}
      </td>
      <td>
        {{ alert.impact }}
      </td>
      <td>
        {{ alert.reason }}
      </td>
     </tr>
    {% if forloop.last == true %}
    </tbody>
  </table>

    {% endif %}
{% else %}
<p>No current service alerts</p>
{% endfor %}

 

## Recently Resolved Service Alerts

This table lists resolved service alerts from the past 30 days. 
[A full list of historical resolved service alerts is available](history/alerts).

{% assign resolved_alerts = site.alerts | where_exp: "alert", "alert.status == 'Resolved'" %}
{% assign date_now = "now" | date: "%s" %}
{% assign date_thresh = date_now | minus: 2592000 | date: "%s" %}
{% assign count = 0 %}
{% for alert in resolved_alerts reversed %}
    {% assign ed = alert.end_date | date: "%s" %}
    {% if ed > date_thresh %}
        {% if count == 0 %}

  <table >
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>Scope</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>
    <tbody>
        {% endif %}
      <tr>
      <td>
        {{ alert.status }}
      </td>
      <td>
        {{ alert.type }}
      </td>
      <td>
        {{ alert.start_date | date: "%Y-%m-%d %H:%M"  }}
      </td>
      <td>
        {{ alert.end_date | date: "%Y-%m-%d %H:%M"  }}
      </td>
      <td>
        {{ alert.scope }}
      </td>
      <td>
        {{ alert.impact }}
      </td>
      <td>
        {{ alert.reason }}
      </td>
      </tr>
        {% assign count = count | plus: 1 %}
    {% endif %}
{% endfor %}
{% if count > 0 %}
    </tbody>
  </table>
{% else %}
<p>No recent service alerts</p>
{% endif %}


## Cirrus Service end

The EPSRC funding for the Cirrus service ended on 31st March 2025. EPCC plan on operating the Cirrus service until later in the year in an at-risk, unsupported mode. If there are any major system issues between we may need to end the service during this period. 


## Service Calendar and Maintenance


This section lists recent and upcoming maintenance sessions. 
[A full list of past maintenance sessions is available](history/maintenance).

{% assign date_now = "now" | date: "%s" %}
{% assign date_thresh = date_now | minus: 2592000 | date: "%s" %}
{% assign count = 0 %}
{% for maint in site.maintenance reversed %}
    {% assign sd = maint.start_date | date: "%s" %}
    {% if sd > date_thresh %}
        {% if count == 0 %}
<div class="table-responsive">
  <table class="table table-striped">
    <thead>
      <tr>
        <th>Status</th>
        <th>Type</th>
        <th>Start</th>
        <th>End</th>
        <th>Scope</th>
        <th>User Impact</th>
        <th>Reason</th>
      </tr>
    </thead>
    <tbody>
        {% endif %}
      <tr>
      <td>
        {{ maint.status }}
      </td>
      <td>
        {{ maint.type }}
      </td>
      <td>
        {{ maint.start_date   }}
      </td>
      <td>
        {{ maint.end_date   }}
      </td>
      <td>
        {{ maint.system }}
      </td>
      <td>
        {{ maint.impact }}
      </td>
      <td>
        {{ maint.reason }}
      </td>
      </tr>
        {% assign count = count | plus: 1 %}
    {% endif %}
{% endfor %}
{% if count > 0 %}
    </tbody>
  </table>
</div>
{% else %}
<p>No scheduled or recent maintenance sessions</p>
{% endif %}




## Maintenance Logs for previous periods

[Previous maintenance logs](history/maintenance)



## At Risk Maintenance Sessions

There is an 'At-Risk' Session provisionally booked every Wednesday from 1000 - 1200. 
A user mailing will be sent if any work is going to take place which may impact users.

### Service Calendar

We maintain a calendar for the Cirrus service that lists upcoming events (such
as training courses and maintenance sessions):

- [Cirrus Service Calendar](calendar.html)

We keep maintenance downtime to a minimum on the service but do occaisionally
need to perform essential work on the system. Maintenance sessions are used to 
ensure that:

* software versions are kept up to date;
* firmware levels on HPE and third-party peripheral equipment are kept up to date;
essential security patches are applied;
* failed/suspect hardware can be replaced;
* new software can be installed;
periodic essential maintenance on HPE electrical and mechanical support equipment (refrigeration systems, air blowers and power distribution units) can be undertaken safely.

Additional maintenance sessions can be scheduled for major hardware or software updates; major upgrades to facility plant and infrastructure; acceptance testing following major service upgrades and statutory electrical testing.

