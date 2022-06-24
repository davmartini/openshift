# Demo for OpenShift Serverless

## Deploy our Application to Knative using kn

1. Create a new space
```
oc new-project kn-demo
```

2. Deploy the application. We will create a Knative Service named fib-knative which will run our fib-knative image on dockerhub.
```
kn service create fib-knative --image docker.io/ibmcom/fib-knative
```
Creating service 'fib-knative' in namespace 'kn-demo':

  0.030s The Route is still working to reflect the latest desired specification.
  0.048s ...
  0.071s Configuration "fib-knative" is waiting for a Revision to become ready.
 20.399s ...
 20.433s Ingress has not yet been reconciled.
 20.474s Waiting for load balancer to be ready
 20.664s Ready to serve.

Service 'fib-knative' created to latest revision 'fib-knative-00001' is available at URL:
https://fib-knative-kn-demo.apps.ocp.drkspace.fr
````

3. Have a description of Knative service
```
kn service describe fib-knative
Name:       fib-knative
Namespace:  kn-demo
Age:        11m
URL:        https://fib-knative-kn-demo.apps.ocp.drkspace.fr

Revisions:  
  100%  @latest (fib-knative-00001) [1] (11m)
        Image:     docker.io/ibmcom/fib-knative (pinned to 9eac25)
        Replicas:  0/0

Conditions:  
  OK TYPE                   AGE REASON
  ++ Ready                  10m 
  ++ ConfigurationsReady    10m 
  ++ RoutesReady            10m 
```

4. Test and charge your application
```
export MY_APP_URL=https://fib-knative-kn-demo.apps.ocp.drkspace.fr
curl -k $MY_APP_URL/5
curl -k $MY_APP_URL/50
curl -k $MY_APP_URL/500
```

