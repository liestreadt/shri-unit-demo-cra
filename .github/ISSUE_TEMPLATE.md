---
title: "Release of [ {{ env.RELEASE_VERSION }} ] version"
labels: Release
---

### Information about release

-   **Version:** {{ env.RELEASE_VERSION}}
-   **Author:** {{ env.RELEASE_AUTHOR }}
-   **Date:** {{ env.RELEASE_DATE | date('dddd, MMMM Do') }}

-   **Changelog**
    {{ env.RELEASE_CHANGELOG}}
