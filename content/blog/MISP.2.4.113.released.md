---
title: MISP 2.4.113 released (aka the bugs fixing marathon)
date: 2019-08-19
layout: post
banner: /img/blog/matrix.jpg
---

# MISP 2.4.113 released

A new version of MISP ([2.4.113](https://github.com/MISP/MISP/tree/v2.4.113)) with tons of fixes and small improvements. We strongly recommend to update to this version.

## API and sync

- [API] get individual server settings via /servers/getSetting/[setting_name], fixes #4964.
- [API] Allow posting freetext data for ingestion via the event UUID instead of ID, fixes #4995.
- [internal / API] new component added to handle repeatable code across all controllers (toolbox controller)
  - added UUID -> ID lookup function and integrated it across several functions
  - fixes #4990
  - fixes #4999
  - fixes #4993
  - fixes #4991
  - fixes #4989
  - fixes #4987
- [sync] Added a protection from receiving empty published events from other instances.
  - a temporary solution to some older, bugged instances emitting them
- [sync] Sync object builder tool fixed.
  - was picking the wrong org as the owner of the remote side
- [sync] Fixed an invalid massaging of object attributes before a sync.
  - on a push, object attributes were not correctly filtered out based on distribution settings
- [API] Attribute add rework. Handle attribute creation in a unified manner via captureAttributes
- Show sharing groups' uuids.
- Delete an object by its uuid, similar syntax to attribute's deletion.
- [stix test] Updated STIX1 test files with the updated MISP event files export results.
- [stix test] Updated MISP event test files with the latest objects supported.
- [logging] Truncate description lengths that would be longer than what
  the DB can store with the default setup.
- [stix export] Change on leveraged ttp at incident level.
  - No longer referencing ttps created out of MISP objects as leveraged ttps at incident level
  - Making sure all ttps, course of actions, threat actors and so on created from MISP galaxies are referenced at incident level
- [six export] Handling vulnerability attributes the same way as objects.
  - Fixing at the same time some references (with vulnerability objects related to vulnerability attributes) that were lost
- [stix export] Better tags handling.
  - Avoid passing event level tags everywhere
  - Using class variable for the tlp markings
- Modules can now pre-check a checkbox from userConfig.
- [types] email-subject added as a valid type for network activity.
  - used to describe outgoing e-mail subjects for exfiltration. Perhaps consider adding a new category for exfiltration altogether.
- [API] servers/serverSettingsEdit now accepts the force parameter in a posted JSON object.
- [API] get organisation by uuid for sightings/listSightings, fixes #4992.
- [API] Misp object delete's uuid lookup fixed.
- [API] removed testing exception.
- [API] Swapped error messages' content from "don't" to "do not" to avoid weird sanitisation artifacts coming from the exception handler.
- [API] error message.
- [API] Attribute edit fixed.
- [API] /galaxies/view by uuid added, fixes #4993.
- [API] sightings restSearch now accepts uuids as org_id, fixes #4992.
- [API] Delete sightings by UUID, fixes #4987.
- [API] /objects/view should accept UUID as a parameter instead of just ID, fixes #4991.
- [API] Delete organisations by UUID, fixes #4989.
- [API] Access event proposals by uuid via shadow_attributes/index/[uuid], fixes #4988.
- [API] Adding an event without the info field set should never work, fixes #4984.

## UI

- [enrichment] Handling correctly comments at objects level.
  - Objects level comments were displayed but not handled at the end, they are now displayed, users can modify them as comments at attributes level, and they are handled then with the saved results
- [UI] Handle settings being removed from config.php more gracefully in the UI.
- [UI] Row description added in View Warninglists.
- [UI] Improved the accessibility of the galaxy matrix view for screen readers. The table elements are now focusable, and only a short text is brailled/spoken by default.

## internal

- [session handling] Session handling fixes.
  - changed the cookie name to MISP-[MISP.uuid] to rely on a unique data-point instead of the URL. This solves issues with multiple MISPs running on the same host via port based virtualhosts
 sharing sessions
  - timeout issues potentially fixed when using the recommended PHP session handler. If the garbage collection is configured in php.ini it could previously purge sessions that based on the session timeout should still be valid
- [debug] Added an on-demand sync debug to assist some debug sessions.
  - very primitives, simply concatenates events to be pushed into a file
- [internal] Default field list added for attributes.
  - let's try to standardised on things we output instead of doing it manually. It's a first step
- [warning-list] Filter CIDR warning list before eval.
- [internal] Potential fix for a race condition generating orphaned attributes, fixes #4886.
  - This fix will avoid issues where the delay is introduced by the deferred start of the execution via the background workers
  - deleting an event whilst data is being actively added will still not be interrupted
- [internal] Feed lookup by UUID removed as feeds don't actually have UUIDs, fixes #4998.

## misp-modules

[misp-modules](https://misp.github.io/misp-modules/) have been improved with new modules especially an improved cuckoo import module (thanks to Pierre-Jean Grenier). The documentation has been also improved (thanks to all the contributors who helped us on the documentation).

[MISP galaxies](/galaxy.html), [MISP object templates](/objects.html) and [MISP warning-lists](https://github.com/MISP/misp-warninglists/) have been updated to the latest version. MISP galaxy now includes a target-location galaxy to improve classification.

We would like to thank all the [contributors](/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large.

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.

