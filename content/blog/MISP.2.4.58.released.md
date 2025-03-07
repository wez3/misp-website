---
title: MISP 2.4.58 released
date: 2016-12-22
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.58](https://github.com/MISP/MISP/tree/v2.4.58) has been released, including bug fixes and a specific improvement to the correlation feature.

![MISP galaxy](/img/blog/correlation.png "{class='img-responsive'}")

Correlation can be disabled at the instance level, or, if a new setting is enabled, at the event or at the attribute level by a site admin or the creator of the event. The latter is an optional feature that can be enabled or disabled system-wide in MISP. This allows for a flexible scheme, supporting situations where the correlations of certain events or attributes are not interesting for the analysts. This feature is also available via the API.

The release includes various improvements such as:

- [Galaxy] bug fixes and improvement to the UI based on users feedback.
- Fuzzy_Hash_Value export added in STIX/CybOX.
- LDAP authentication improved to get role from LDAP.
- Some minor bug fixes and updates.

A big thanks to all the users who gave feedback and contributors who helped us improve MISP.

The full change log is available [here](http://www.misp-project.org/Changelog.txt).

A [MISP training is organized the 7th February 2017 in Luxembourg](https://www.eventbrite.com/e/misp-training-tickets-30484201066) and a [hackathon the 8th February 2017](https://www.eventbrite.com/e/misp-hackathon-3-tickets-30488596212).

Don't hesitate to [open an issue](https://github.com/MISP/MISP/issues) if you have any feedback, found a bug or want to propose new features.
