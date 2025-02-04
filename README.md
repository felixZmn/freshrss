# FreshRSS

A helm chart for [FreshRSS](https://freshrss.org/) - a free, self-hostable aggregator.

## build the chart

```bash
helm package .
helm registry login ghcr.io -u felixZmn

export CHART_VERSION=$(grep -m 1 'version:' ./Chart.yaml | tail -n1 | awk '{ print $2 }')
helm push ttrss-${CHART_VERSION}.tgz oci://ghcr.io/felixzmn/helm
```
