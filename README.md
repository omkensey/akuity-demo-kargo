# Kargo Quickstart Template

These are the supporting files for [the Kargo Quickstart tutorial](https://docs.akuity.io/tutorials/kargo-quickstart/) in the Akuity docs.

This tutorial will walk you through a working example using Kargo with the Akuity Platform, to manage the promotion of an image from stage to stage in a declarative way.

Ultimately, you will have a Kubernetes cluster, with Applications deployed using an Argo CD control plane; and handle promotion with Kargo.

This instance adds a `dev-debug` stage, as an example of using a promotion to deploy a debug sidecar:
- The dev-debug stage is subscribed to the dev stage.
- The debug sidecar (`fedora` was used for simplicity) is inserted via a new Kustomize base file statically including the container just to quickly demonstrate the capability; alternately it could be deployed as additional Freight, which would allow deploying different versions of the debug sidecar or potentially even entirely different debug sidecars easily.
- In the interest of simplicity, the argo-cd step was not customized for that stage.