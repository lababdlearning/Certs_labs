# Heml commnds
```
helm package demoapp-chart
helm registry login quay.io #labandlearning:pass
helm push demoapp-chart-0.1.0.tgz oci://quay.io/labandlearning/demo-chart
 Pushed: quay.io/labandlearning/demo-chart/demoapp-chart:0.1.0
 Digest: sha256:1aebf737169f0150f7a818ceff9229c1526e7c0e9b645d477e5784a4c8789eb8
helm install helmdemo oci://quay.io/labandlearning/demo-chart/demoapp-chart --version 0.1.0
helm list
helm uninstall helmdemo
```
