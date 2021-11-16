# why kubernetes
As far as I understand, Kubernetes is for orchestrating the things that have more advantages than provisioning in the traditional way.

If we have more applications and that applications need to migrate from on premise to cloud and maintain availability with zero downtime. We can go with Kubernetes.

Instead of maintaining docker containers, and the control plane, Google provided with GKE service where these both will be maintained by Google SRE team. We can use this GKE to create a cluster with master and minion nodes. where we can use this master node to deploy apps on the nodes and make this available or expose to the internet using the service ( Load balancer).

Probably, this leads to eliminate latency and improves the Scalability and availability of the applications.

# master components

Scheduler - assigns your application to the worker node

Api server - communication hhub for the cluster components. It exposes the kubernetes API

etcd. - stores all the configuration

contoller manager - Maintaining cluster, handles node failures, replicating components, maintaing the correct amount of pods

# worker components

Kubectl  - runs and manage the containers on the cluster and talks to the API server

kube-proxy - load balances the traffic b/w application components

container runtime - the program that runs your container

# A deployment is an object in Kubernetes that lets you manage a set of identical pods.

Without a deployment, you’d need to create, update, and delete a bunch of pods manually.

With a deployment, you declare a single object in a YAML file. This object is responsible for creating the pods, making sure they stay up to date, and ensuring there are enough of them running.

# deployment strategies

Blue-Green Deployment - When deploying a new version of an application, a second environment is created. 
                        Once the new environment is tested, it takes over from the old version. The old environment can then be turned off.
                        
A/B Testing - Two versions of an application are running at the same time. A portion of requests go to each. Developers can then compare the versions.  

Canary Release - A new version of a microservice is started along with the old versions. 
                 That new version can then take a portion of the requests and the team can test how this new version interacts with the overall system.
                 
https://opensource.com/article/17/5/colorful-deployments

# service vs Ingress Vs deployment  
https://dwdraju.medium.com/how-deployment-service-ingress-are-related-in-their-manifest-a2e553cf0ffb


# Replicaset
ReplicaSets are a higher-level API that gives you the ability to easily run multiple instances of a given pod. You tell the ReplicaSets the number of pods that you want it to run and it will ensure that the exact number of pods are actually running.

1 # Service
Service is an abstraction which defines a logical set of Pods and a policy by which to access them
In Kuberenetes we have 4 types of services.

1.1 # ClusterIP. 
This default type exposes the service on a cluster-internal IP. You can reach the service only from within the cluster.

1.2 # NodePort. 
This type of service exposes the service on each node’s IP at a static port. A ClusterIP service is created automatically, and the NodePort service will route to it. From outside the cluster, you can contact the NodePort service by using “<NodeIP>:<NodePort>”.

1.3 # LoadBalancer. 
This service type exposes the service externally using the load balancer of your cloud provider. The external load balancer routes to your NodePort and ClusterIP services, which are created automatically.

# ExternalName. 
This type maps the service to the contents of the externalName field (e.g., foo.bar.example.com). It does this by returning a value for the CNAME record.


# What you did with Kubernetes?
    Worked on setting up Docker Orchestration platform. Kubernetes for deployment of Docker containers on a large scale.
    Managed Kubernetes minions & masters to patch with latest security updates by evicting and uncording the nodes during the process.
    Managed local deployments in Kubernetes, creating local cluster and deploying application containers.
    Container management using Docker by writing Dockerfiles and set up the automated build on Docker HUB and installed and configuredKubernetes.
        
# Kubernetes Issues:
    some major issues with Kubernetes I came across was like 
    1. etcd member has no leader,  etcd is not available, or controller manager is unavailable, 
       Scheduler is unavailable. So these are the kind of issues I worked on before. 
       
# Monitoing
    Yes, basically in order to ensure any kind of like CPU usage or memory usage. I purposefully monitoring that using like application performance monitoring tools, using like APP dynamics. New Relic in order to ensure like average response time, load management and error checks and basically for setting up a high availability Kubernetes master are used to manage our Kubernetes master replicating that on different availability zones.
        
# Load Balancing Techniques
    So basically, I have used like Ingress controllers for load balancing techniques. basically for eliminating SSL and punch termination.


1. We use like custom resource definition file for "versioning within object persistent level".

2. Yes, we are using like persistent volumes have used like Trident and port walks. 

3. So, usually we can utilize any kind of like CNI methodology, like the container network interface. 
   Using like Calico or funnel,  so that where we can allocate like specific IP address with a specific namespaces in order to route the traffic 
   for a specific cluster.
   
# For code coverage static analysis, I have used like sonar cube, and veracode.

# Well basically we will be running up the all the configuration files like pulling data from the "Log Stash and storing that within Elasticsearch".



