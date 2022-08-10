# GitHub Action to Generate Developer Meeting Slides
[![Test](https://github.com/wdconinc/generate-meeting-slides/actions/workflows/test.yml/badge.svg)](https://github.com/wdconinc/generate-meeting-slides/actions/workflows/test.yml)

This GitHub Action produces developer meeting slides with issues, PRs, etc..., during a specified period.

## Instructions

### Prerequisites
This action has no prerequisites.

### Example

You can use this GitHub Action in your own repository with `uses: eic/generate-meeting-slides@v1`.

A minimal job example for GitHub-hosted runners of type `ubuntu-latest`:
```yaml
on:
  schedule:
    - cron:  '30 8 * * 3' # 08:30 UTC on Wednesday
  workflow_dispatch:

jobs:
  generate-weekly-meeting-slides:
    runs-on: ubuntu-latest
    steps:
    - uses: eic/generate-meeting-slides@v1
      with:
        interval: "week"
```
