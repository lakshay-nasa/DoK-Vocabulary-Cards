# StatefulSets

Know More Here - [StatefulSet](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)
<img src="Images\StatefulSet.png">


# Custom Resource

Custom Resources -

As the name suggests, the resources are not present by default in the Kubernetes cluster. In Kubernetes, there are a set of pre-defined resources. Such as pods, deployments, etc. But cloud Native, Ecosystem contains lots of different tools which help to increase Kubernetes API. Those external resources are called Custom Resources.

CRD -

We use Custom Resource Definitions to register Custom Resources in Kubernetes Cluster.

Example -

Let's say you register a CRD of type "PostgresCluster" to represent Postgres Clusters. Then you create two "PostgresCluster" named  ```cluster1``` and ```cluster2```. Here ```cluster1``` is a CR, an "instantiation" of the CRD. A CRD is how you define, register to Kubernetes, how your custom resources want to be.

Know More Here - [Custom Resources](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)
<img src="Images\Custom-Resource.png">


# Stateful Vs Stateless

:round_pushpin: <b> Stateful App </b> -
When we speak of stateful apps, state refers to any data the app needs to store to function as designed.
An example of a stateful app would be an online shop that remembers your cart is a stateful app.
<img src="Images\Stateful-App.png">

:round_pushpin: <b> Stateless App </b> -
A stateless app is an application program that does not save client data generated in one session for use in the next session with that client.
An example of a stateless would be searching online to answer a question. You type your question into a search engine and hit enter. If accidentally your search is interrupted or closed, you have to start a new one.
<img src="Images\Stateless-App.png">

:rocket: Check out a talk by <b> Kunal Verma </b> from <i> DoK Student Day 2021 </i>, about Stateful and Stateless - https://www.youtube.com/watch?v=YlN2BM_nuCE

:male-technologist: It can be terrifying to deploy your first ever stateful app in Kubernetes, <b> Steve Buchanan </b> in his session at <i> DoK Talk #121 </i> shares some best practices, and a demo of deploying a Stateful App - https://www.youtube.com/watch?v=lDhRgdcZDrs

# Operators

### Why do we need Operators in Kubernetes?

Operators are used mainly for Stateful Applications. Kubernetes can manage the complete lifecycle of Stateless Apps as there is no logic required for running and maintaining them. So, K8's can automatically create, update, delete and maintain these applications. Whereas for Stateful Apps, Kubernetes internally doesn't have the knowledge to automate the process of deploying every single stateful application. Hence, it uses extensions named operators.

We know it can be complex to write your first operator. But we got you covered Julian Fischer in his talk at DoK day North America 2021 @KUBECON, talks about - Principles for building Operators.

Link to the session - https://www.youtube.com/watch?v=idHGkaK0OTg

Know More Here - [Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
<img src="Images\Operators.png">

# Namespaces

### Why do we use Namespace in Kubernetes?

Namespace provides an additional qualification to a resource name. It is helpful when multiple teams use the same cluster and there is a possibility of name collision. It can act as a virtual wall between multiple clusters.

Features of Namespace -
   * Namespaces help pod-to-pod communication using the same namespace.
   * Namespaces are virtual clusters that can sit on top of the same physical cluster.
   * They provide logical separation between the teams and their environments.
  
Know More - https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/
<img src="Images\Namespaces.png">

# Kubernetes Volume

### What problem does Kubernetes volume solve?
On-disk files in a container are transient, which raises some problems for non-trivial applications when running in containers.
1. The loss of files when a container crashes. The kubelet restarts the container but with a clean state.
2. The second problem occurs when sharing files between containers running together in a Pod.
The Kubernetes volume abstraction solves both of these problems. :sparkles:

Kubernetes supports several types of volumes. Know about them here - https://kubernetes.io/docs/concepts/storage/volumes/
<img src="Images\Volume.png">

# Persistent Volumes

### Why do we need PVs?
The most common use case for Persistent volumes in Kubernetes is for databases. Containers are immutable, meaning that when a container shuts down, all data created during its lifetime is lost. This works for some applications, but most applications need to preserve the state.
To ensure that data persists well beyond a container???s lifecycle, the best practice is to separate data storage from containers.

???Vanshika Srivastava, in her talk at DoK Student Day 2021, explains persistence in Kubernetes - https://www.youtube.com/watch?v=C8VxdczAS_I

Know more about PVs here - https://kubernetes.io/docs/concepts/storage/persistent-volumes/
<img src="Images\Persistent-Volumes.png">

# Storage Classes

### What's so interesting about Storage Classes? ????

Storage classes are created as part of the bootstrapping of the Kubernetes cluster by the administrator. The major goal of storage classes is to eliminate the need for cluster administrators to pre-provision storage and allow them to be created on-demand. Users can then request storage by specifying the storage class and the size of the volume needed in their claims.

  * StorageClass allows dynamic provisioning of Persistent Volumes, when PVC claims it.
  * StorageClass abstracts underlying storage provider.
  * StorageClass is used in conjunction with PVC that allow Pods to dynamically request a new storage.

Know more - https://kubernetes.io/docs/concepts/storage/storage-classes/

<img src="Images\Storage Classes.png">

# ReplicaSet

### Why do we need a Replication in Kubernetes?
  There are several reasons for this -

  * Reliability: Having multiple versions of an application prevents problems like if one or more fail. It is true if the system replaces any containers that fail.
  * Load balancing: Having multiple versions of a container enables you to send traffic to different instances to prevent the overloading of a single instance or node. It is something that Kubernetes does out of the box, making it extremely convenient.
  * Scaling: When a load becomes too much for the number of existing instances, Kubernetes enables you to scale up your application, adding additional instances as needed.

Know more here - https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/

<img src="Images\ReplicaSet.png">

# Services

### Why Services in Kubernetes?
Since pods are ephemeral, a service enables a group of pods, which provide specific functions (web services, image processing, etc.) to be assigned a name and unique IP address (clusterIP). As long as the service is running that IP address, it will not change. Services also define policies for their access. :tanabata_tree:

Know more here - :rocket: https://kubernetes.io/docs/concepts/services-networking/service/

<img src="Images\Service.png">

# Container

### What are the benefits of containers?
Containers are lightweight packages of your application code together with dependencies such as specific versions of programming language runtimes and libraries required to run your software services.

Here are some of the most common reasons developers decide to use containers:
* Portability
* Efficiency
* Agility
* Faster delivery
* Improved security
* Faster app start-up
* Easier management
* Flexibility

:sparkles: Know more here - https://glossary.cncf.io/container/ 

<img src="Images\Containers.png">

# Pod

We can consider a Pod to be a self-contained, isolated "logical host" that contains the systemic needs of the application it serves. A Pod is meant to run a single instance of your application on your cluster. However, it is not recommended to create individual Pods directly. Instead, you generally create a set of identical Pods, called replicas, to run your application.

Pods Lifecycle -
* Pods are ephemeral. They are not designed to run forever, and when a Pod is terminated it cannot be brought back. In general, Pods do not disappear until they are deleted by a user or by a controller.
* Pods do not "heal" or repair themselves. For example, if a Pod is scheduled on a node which later fails, the Pod is deleted. Similarly, if a Pod is evicted from a node for any reason, the Pod does not replace itself.

:sparkles: Know more - https://kubernetes.io/docs/concepts/workloads/pods/

<img src="Images\Pod.png">

# Node
There are three main node components -
* kubelet - An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod.
* kube-proxy - kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.
* Container runtime - The container runtime is the software that is responsible for running containers.
  
      Node components run on every node, maintaining running pods and providing the Kubernetes runtime environment.
  
????: Know more here - https://kubernetes.io/docs/concepts/architecture/nodes/

<img src="Images\Node.png">

# Deployments

Deployments represent a set of multiple, identical Pods with no unique identities. In this way, Deployments help ensure that one or more instances of an application are available to serve user requests.

Deployments vs StatefulSets

* Deployments are used for stateless applications, StatefulSets for stateful applications
* The pods in a deployment are interchangeable, whereas the pods in a StatefulSet are not.
* In StatefulSet pods names are in sequential order on the other hand in deployment pods names are unique.

:sparkles: Know more here - https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

<img src="Images\Deployments.png">

# DaemonSets

DaemonSets are an integral part of the Kubernetes cluster facilitating administrators to easily configure services (pods) across all or a subset of nodes.

:round_pushpin: DaemonSet use cases -
* running a cluster storage daemon on every node
* running a logs collection daemon on every node
* running a node monitoring daemon on every node

:rocket: Know more here - https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/

<img src="Images\DaemonSet.png">

# Kubernetes Jobs

Kubernetes features several controllers for managing pods. We have ReplicaSets, DaemonSets, StatefulSets, and Deployments. Each one of those has its own scenario and use case. However, they all share one common property: they ensure that their pods are always running. If a pod fails, the controller restarts it or reschedules it to another node to make sure the application the pod is hosting keeps running.

What if we do want the pod to terminate? There are many scenarios when you don???t want the process to keep running indefinitely.

    Kubernetes Jobs ensure that one or more pods execute their commands and exit successfully. When all the pods have exited without errors, the Job gets completed. When the Job gets deleted, any created pods get deleted as well.
    
:sparkles: Know More here - https://kubernetes.io/docs/concepts/workloads/controllers/job/

<img src="Images/Jobs.png">

# ReplicationController

Have you ever wondered what supervises and manages just the exact number of pods running inside the Kubernetes cluster? Kubernetes can do this in multiple ways, but one common approach is using the ReplicationController. A ReplicationController is responsible for managing the pod lifecycle and ensuring that the specified number of pods required are running.

PS.:memo: Replication Controller is being replaced by Replica Sets, but it???s still in wide use, so it???s worth understanding what it is and how it works. A Replication Controller is a structure that enables you to easily create multiple pods, and then make sure that the number of pods always exists.

:sparkles: Know More Here - https://kubernetes.io/docs/concepts/workloads/controllers/replicationcontroller/

<img src="Images/ReplicationController.png">

# ConfigMap

Why would you use ConfigMap in Kubernetes?

Use a ConfigMap to keep your application code separate from your configuration. A ConfigMap stores configuration settings for your code. Store connection strings, public credentials, hostnames, and URLs in your ConfigMap. However, they are not suitable for confidential data storage. ConfigMaps are not encrypted, and all data they contain is visible to anyone who can access the file. You can use Kubernetes secrets to store sensitive information.

:bookmark:Know More Here - https://kubernetes.io/docs/concepts/configuration/configmap/

<img src="Images/ConfigMap.png">
