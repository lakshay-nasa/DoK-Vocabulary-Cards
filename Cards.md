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
To ensure that data persists well beyond a container’s lifecycle, the best practice is to separate data storage from containers.

✨Vanshika Srivastava, in her talk at DoK Student Day 2021, explains persistence in Kubernetes - https://www.youtube.com/watch?v=C8VxdczAS_I

Know more about PVs here - https://kubernetes.io/docs/concepts/storage/persistent-volumes/
<img src="Images\Persistent-Volumes.png">
