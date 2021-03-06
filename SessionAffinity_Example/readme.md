

# Helloworld service (istio session affinity example)

We will distribute load with session affinity within the scope of istio-example

This sample includes two versions(v1,v2) of a simple helloworld service that returns its project version when called. It can be used as a test service when experimenting with version routing.

This service is also used to demonstrate  session affinity deployments working in conjunction. See  session affinity deployments using Istio. Code repo for image [github\dotnet-example](https://github.com/OktaySavdi/dotnet-example)

## Start the helloworld service

The following commands assume you have [automatic sidecar injection](https://istio.io/docs/setup/additional-setup/sidecar-injection/#automatic-sidecar-injection) enabled in your cluster. If not, you'll need to modify them to include [manual sidecar injection](https://istio.io/docs/setup/additional-setup/sidecar-injection/#manual-sidecar-injection).


Deploying version v1, v2, or both:
```ruby
kubectl create -f SessionAffinity_Example/
```
![https://github.com/OktaySavdi/istio-examples/new/master/SessionAffinity_Example](https://user-images.githubusercontent.com/3519706/74125496-8ab68480-4be6-11ea-8839-a9855d951440.png)

## Generate load
```ruby
while true; do curl -s "http://[URL]/istio"; sleep 0.5; echo -e '\n'; done
    
while true; do curl -s "http://myapps.mycluster.com/istio"; sleep 0.5; echo -e '\n'; done 
```
## Monitoring and Control

**Control istio Config**

![image](https://user-images.githubusercontent.com/3519706/116877626-dcea2800-ac26-11eb-8e6a-53aeb8aad995.png)

**Control Graph**

![https://github.com/OktaySavdi/istio-examples/new/master/SessionAffinity_Example](https://user-images.githubusercontent.com/3519706/73925864-c1875480-48df-11ea-9a6a-cb4df50250e5.png)

**Overview Console**

![https://github.com/OktaySavdi/istio-examples/new/master/SessionAffinity_Example](https://user-images.githubusercontent.com/3519706/73649574-1f722d00-4691-11ea-8f8f-f9ce8f21b4fa.png)

**Inbound Metrics**

![https://github.com/OktaySavdi/istio-examples/new/master/SessionAffinity_Example](https://user-images.githubusercontent.com/3519706/73649621-3d3f9200-4691-11ea-9a4f-d12737d9c59a.png)

**CLI on Server**

![https://github.com/OktaySavdi/istio-examples/new/master/SessionAffinity_Example](https://user-images.githubusercontent.com/3519706/74103657-fa812c80-4b5e-11ea-951e-600616d0a045.png)
