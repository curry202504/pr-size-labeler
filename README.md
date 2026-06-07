# PR Size Labeler

[![GitHub release](https://img.shields.io/github/v/release/curry202504/pr-size-labeler)](https://github.com/curry202504/pr-size-labeler/releases)

Automatically label pull requests based on the number of lines changed.

## Usage

```yaml
name: PR Size Label
on:
  pull_request:
    types: [opened, synchronize, reopened]
jobs:
  label:
    runs-on: ubuntu-latest
    steps:
      - uses: curry202504/pr-size-labeler@v1
        with:
          github-token: {% raw %}${{ secrets.GITHUB_TOKEN }}{% endraw %}
```

## Labels

| Size | Lines | Label |
|------|-------|-------|
| XS | 1-10 | size/xs |
| S | 11-50 | size/s |
| M | 51-200 | size/m |
| L | 201-500 | size/l |
| XL | 500+ | size/xl |

## Inputs

| Input | Required | Default | Description |
|-------|----------|---------|-------------|
| github-token | Yes | — | GitHub token for API access |
| xs-max | No | 10 | Max lines for XS label |
| s-max | No | 50 | Max lines for S label |
| m-max | No | 200 | Max lines for M label |
| l-max | No | 500 | Max lines for L label |

---

Published by Lobster Dev
