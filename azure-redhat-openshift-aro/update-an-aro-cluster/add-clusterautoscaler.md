# Add ClusterAutoscaler

oc apply -f clusterautoscaler.yaml

```
apiVersion: autoscaling.openshift.io/v1
kind: ClusterAutoscaler
metadata:
  name: default
spec:
  podPriorityThreshold: -10 
  resourceLimits:
    maxNodesTotal: 24 
  scaleDown: 
    enabled: true 
    delayAfterAdd: 10m 
    delayAfterDelete: 5m 
    delayAfterFailure: 30s  
```
