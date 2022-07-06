# Cluste logging

Understand cluster logging in Openshift\
[https://docs.openshift.com/container-platform/4.6/logging/cluster-logging.html](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging.html)

* Kibana for visualization\
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-visualizer.html#cluster-logging-visualizer](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-visualizer.html#cluster-logging-visualizer)
* Configure log collector\
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-deploying.html#cluster-logging-deploying](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-deploying.html#cluster-logging-deploying)
* JSON logging\
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging.html#cluster-logging-json-logging-about\_cluster-logging](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging.html#cluster-logging-json-logging-about\_cluster-logging)
* Kubernetes Events Router\
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-eventrouter.html#cluster-logging-eventrouter](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-eventrouter.html#cluster-logging-eventrouter)
* Openshift Container Platform logging\
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-upgrading.html#cluster-logging-upgrading](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-upgrading.html#cluster-logging-upgrading)
* Uninstalling cluster logging \
  [https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-uninstall.html#cluster-logging-uninstall](https://docs.openshift.com/container-platform/4.6/logging/cluster-logging-uninstall.html#cluster-logging-uninstall)

## Major components of cluster logging

### Collector

Deployed on each node to collect node and pod logs. OCP 4.6 uses Fluentd as collector.&#x20;

### Log store

Default is Elasticsearch which tested and optimized for short-term storage

### Kibana

Visualization





1.
