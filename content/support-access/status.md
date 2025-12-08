---
layout: single
title: Cirrus Service Status
summary: Up to date status of the Cirrus service
---


- [Current System Load](#current-system-load)
- [Service Alerts](#service-alerts)
- [Service Maintenance Sessions](#service-maintenance-sessions)

## Current System Load

The plot below shows the status of the CPU nodes on the current Cirrus service for the past day
(note: the Cirrus GPU nodes are not included in this plot).

A description of each of the status types is provided below the plot.

### CPU

![Cirrus Node Status graph](https://safe.epcc.ed.ac.uk/Graphs/cirrus_ex.png)

- *alloc*: Nodes running user jobs
- *idle*: Nodes available for user jobs
- *resv*: Nodes in reservation and not available for standard user jobs
- *down*, *drain*, *maint*, *drng*, *comp*: Nodes unavailable for user jobs
- *mix*: Nodes in multiple states 

## Service Alerts

{{< open-alerts >}} 

### Recently Resolved Service Alerts

This table lists the last five resolved service alerts 
[A full list of historical resolved service alerts is available](../history/alerts/).

{{< recent-alerts >}} 

## Service Maintenance Sessions

We keep maintenance downtime to a minimum on the service but do occasionally
need to perform essential work on the system. Maintenance sessions are used to 
ensure that:

* software versions are kept up to date;
* firmware levels on HPE and third-party peripheral equipment are kept up to date;
essential security patches are applied;
* failed/suspect hardware can be replaced;
* new software can be installed;
periodic essential maintenance on HPE electrical and mechanical support equipment (refrigeration systems, air blowers and power distribution units) can be undertaken safely.

Additional maintenance sessions can be scheduled for major hardware or software updates; major upgrades to facility plant and infrastructure; acceptance testing following major service upgrades and statutory electrical testing.

{{< open-maintenance >}} 

A list of all [previous maintenance sessions](../history/maintenance/).



