---
title: MISP 2.4.111 released (aka improved proposal sync)
date: 2019-07-19
layout: post
banner: /img/blog/comid.jpeg
---

# MISP 2.4.111 released

A new version of MISP ([2.4.111](https://github.com/MISP/MISP/tree/v2.4.111)) has been released with an improved proposal sync, minor improvements and bugs fixed.

## Proposal synchronisation rework

The proposal synchronisation has undergone a long over-due rewrite and as a result it has been significantly improved compared to the original implementation, which was released several years ago. We strongly invite all users of MISP to upgrade
to the latest version to restore the fetch-on of proposals via the synchronisation. The proposal index has been reworked and proposal pull is now limited to the last 14 days (to avoid trying to pull ancient proposals at each sync).

## New attribute type community-id added

At the MISP project, we are big supporters of new open standards, which can help communities in an effort to reference forensic evidences, especially network forensic evidences. It has always been difficult to track down common network flows as many tools and products rely on different methods to build network flow ids. [Christian Kreibich](https://github.com/ckreibich) from Corelight decided to take a bash at resolving this issue and has been working on creating the [Community ID Flow Hashing](https://github.com/corelight/community-id-spec) format. As the community-id is open to open source implementations which can be reused, various open source projects already support it such as Zeek (Bro), Suricata, Moloch, HELK, Elastic and now also MISP, as of version 2.4.111.

In 2.4.111, a new attribute type has thus been added, along with the following object templates already including the new attribute field:

- [Netflow](/objects.html#_netflow)
- [Network connection](/objects.html#_network_connection)

This feature allows to easily correlate network forensic flows from different tools or network equipment.

## Improvements and bugs fixed

- [misp-modules enrichment] Fixed index in attribute.
- [API] Deletes broken due to invalid boolean.
- [API] Delete http method/requests properly accepted by some /delete endpoints.
- [sync] Fixed a bug breaking the synchronisation between MISP instances.
- [stix2] Import of User Account objects is now supported.
- Issues #4864, #4861, #4847 fixed

[MISP galaxy](/galaxy.html), [MISP object templates](/objects.html) and [MISP warning-lists](https://github.com/MISP/misp-warninglists/) have been updated to the latest version.

We would like to thank all the contributors, reporters and users who have helped us in the past months to improve MISP and information sharing at large.

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.

