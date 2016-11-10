---
layout: page
title: Releases (EN)
wikiPageName: Releases-(EN)
menu: wiki
---

## Branches 
The recalbox-buildroot git branches are created this way :  
- the **unstable** branch for a version is the most recent version identified : _rb-4.0.X_.  The new code is pushed on this branch.  
- when a major release must be done (**4.0.0**), a new branch is created (_rb-4.1.X_) and the _rb-4.0.X_ branch is stabilized (all buildroot packages versions are locked to a commit or branch).  
- for a minor version of a stabilized branch, release and tags will be sufficient.

## Builds and releases
- the **_unstable_** builds are created each night on the current _unstable_ branch.  
- the **_beta_** images are created with the last _unstable_ that have been tested and working.  
- the **_stable_** images are created with the image of a _beta_ that is candidate for a stable release.  

## Recalbox updates
The recalboxOS can be configured to make it's updates from one of the three levels :  
The recalbox.conf `updates.type` can be set to `stable`, `beta` or `unstable`.

## Recalbox archive  
The http://archive.recalbox.com/4/ contains the following files :  

- rpi1/
    - stable/
        - last -> the link to the last rpi1 stable release
    - beta/
        - last -> the link to the last beta release
    - unstable/
        - last -> the link to the last unstable release
        - recalbox-unstable-4.1.X-20150217/
        - recalbox-unstable-4.1.X-20150210/
        - recalbox-unstable-4.1.X-20150201/
- rpi2/
    - stable/
        - last -> the link to the last rpi2 stable release
    - beta/
        - last -> the link to the last beta release
    - unstable/
        - last -> the link to the last unstable release
        - recalbox-unstable-4.1.X-20150217/
        - recalbox-unstable-4.1.X-20150210/
        - recalbox-unstable-4.1.X-20150201/

The `system.updates.version` will define the path of the directory to look for. Then the `recalbox.version` file in each release directory will be compared to the local `recalbox.version` file.

