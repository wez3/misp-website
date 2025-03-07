---
title: MISP 2.4.61 released
date: 2017-01-22
layout: post
banner: /img/blog/misp-small.png
---

A new version of MISP [2.4.61](https://github.com/MISP/MISP/tree/v2.4.61) has been released, including a critical bug fix, new features and minor updates. We strongly recommend to update MISP to this latest version.

![MISP warning-list](/img/blog/warning-list.png "{class='img-responsive'}")

[Warning lists](https://github.com/MISP/misp-warninglists) has been significantly updated with two new types: ```hostname``` and ```substring```. This allows
to make more granular matching to find additional potential false-positives. The ```hostname``` type allows smart substring matching within URLs.

A critical bug was fixed (introduced in 2.4.60) that could lead to an attribute being dropped from an event on import.

The release includes further improvements such as:

- Some improvements to the screenshot view as attribute to expand/collapse its view.
- A new API has been added to [manage organisations via the ReST API](https://www.circl.lu/doc/misp/automation/index.html#organisation-management).
- [taxonomies and galaxy] updated to the latest version.
- UTF8 encoding is now enforced at the default database config.

A big thanks to all the users who gave feedback and contributors who helped us improve MISP.

The full change log is available [here](https://www.misp.software/Changelog.txt).

Don't hesitate to [open an issue](https://github.com/MISP/MISP/issues) if you have any feedback, found a bug or want to propose new features.
