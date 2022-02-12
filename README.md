# MyOpenShift

My OpenShift



## Pipeline


```dos
oc
oc get pods -n openshift-console | grep console
oc get routes console -n openshift-console
oc apply -f /opt/operator/subscription.yaml
```


subscription.yaml

```yml
apiVersion: operators.coreos.com/v1alpha1
kind: Subscription
metadata:
  name: openshift-pipelines-operator
  namespace: openshift-operators
spec:
  channel: stable
  name: openshift-pipelines-operator-rh
  source: redhat-operators
  sourceNamespace: openshift-marketplace
```

```dos
until oc api-resources --api-group=tekton.dev | grep tekton.dev &> /dev/null
do
 echo "Operator installation in progress..."
 sleep 5
done

echo "Operator ready"
```


![](image/README/001.png)

![](image/README/002.png)

![](image/README/workloads_Pods.png)

![](image/README/workloads_Deployments.png)


DeploymentConfigs

StatefulSets

![](image/README/workloads_Secrets.png)

![](image/README/workloads_ConfigMaps.png)

![](image/README/networking_storage.png)

![](image/README/003.png)

![](image/README/004.png)





