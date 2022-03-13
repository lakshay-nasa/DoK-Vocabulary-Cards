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


# Operators

Know More Here - [Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
<img src="Images\Operators.png">
