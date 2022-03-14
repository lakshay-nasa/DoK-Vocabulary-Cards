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

Know More Here - [Operators](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/)
<img src="Images\Operators.png">
