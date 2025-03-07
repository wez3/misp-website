---
title: MISP 2.4.145 and 2.4.146 released (Improved warning-lists)
date: 2021-07-05
layout: post
banner: /img/blog/warning-lists.png
---

# MISP 2.4.145 and 2.4.146 released

MISP 2.4.145 and 2.4.146 released including a massive update to the MISP warning-lists, various improvements and security fixes.

# MISP warning-lists improvements.

[Warning lists](https://github.com/misp/misp-warninglists) system has been significantly improved (thanks to Jakub Onderka).

- Custom warning lists can be created and managed in the MISP user-interface
- Warning lists can be now imported via the API
- Warning lists changes are exported in the ZMQ channel
- Warning lists include new categories to describe the scope

# New features

## Summary email notification

Email notifications have received a new configuration setting: New event summaries only.
This feature publishes the normal alert reports excluding attributes and objects, thereby
only describing a summary of the alert. This can be used when encryption cannot be enabled
and organisations still require email alerting.

## Documentation

New documentation has been added to describe the [session and cookie handling in MISP](https://raw.githubusercontent.com/MISP/MISP/2.4/docs/generic/Authentication%20Diagram/MISP%20Authentication%20Diagram.png).

## API

- Thanks to a new feature, you can now create read only authentication keys (don't forget to enable the advanced authentication key feature for this to work).

# Security Fixes

- Various fixes regarding XSS and potential escaping issues including [CVE-2021-35502](https://cvepremium.circl.lu/cve/CVE-2021-35502) and [CVE-2021-36212](https://cvepremium.circl.lu/cve/CVE-2021-36212).

Thanks to the reporters including Nicolas Vidal from TEHTRIS.

# Various improvements

- [OpenAPI] - Missing return formats added to the documentation
- [server caching] only push data to redis / logs if there's something to push
- [attribute] validation tightened for empty strings. A value containing only control characters will now be blocked from entry.
- [feeds] Added 3 daily feeds (ssh bruteforce, telnet bruteforce, URLs seen)  from the APNIC Community Honeynet Project

# Acknowledgement

We would like to thank all the [contributors](/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large. This release includes multiple updates in [misp-objects](/objects.html), [misp-taxonomies](/taxonomies.html) and [misp-galaxy](/galaxy.html)
.

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.

