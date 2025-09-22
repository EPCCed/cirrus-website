---
layout: single
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---

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

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 

### GPU
![Cirrus GPU Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus_gpu.png)

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 



## Known Issues 

We are experiening a heavy load on the metadata server. Our systems team are investigating but we suspect this is due to user(s) performing many I/O operations. We apologise for the inconvenience this is causing users. 

## Service Alerts

TBD
 

## Recently Resolved Service Alerts

This table lists resolved service alerts from the past 30 days. 
[A full list of historical resolved service alerts is available](history/alerts).

TBD

## Cirrus Service end

The EPSRC funding for the Cirrus service ended on 31st March 2025. EPCC plan on operating the Cirrus service until later in the year in an at-risk, unsupported mode. If there are any major system issues between we may need to end the service during this period. 


## Service Calendar and Maintenance

TBD

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

