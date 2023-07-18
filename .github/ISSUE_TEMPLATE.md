---
title: "Release of [ {{ env.RELEASE_VERSION }} ] version"
labels: Release
---

## Information about release

-   **Version:** {{ env.RELEASE_VERSION}}
-   **Author:** {{ env.RELEASE_AUTHOR }}
-   **Date:** {{ env.RELEASE_DATE | date('dddd, MMMM Do, yyyy') }}

## Changelog

**Changes compare to previous release**
{{ env.RELEASE_CHANGELOG }}

## Tests result

Tests result № **{{ env.RELEASE_TESTS_NUM }}**
{{ env.RELEASE_TESTS_RESULT_MSG }}
