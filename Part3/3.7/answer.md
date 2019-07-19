# When (not) to use Kubernetes

If your solution is based on containers (only) and it needs to scale, heal and update in a controlled fashion, **Kubernetes** is a safe choice. It has already been tested by many enterprises with large scale solutions, hence it has become flexible and has reached maturity as a product. Currently it has a healthy community to help noobies and develop it further. It is well suited for large scale and/or complex configurations, but can be run on a single host still if absolutely needed. This comes with a price: setting it up and configuring (all) the application(s) can be a very long process if a person/team has no prior experience with it.

For small(er) configurations **Docker Swarm** may be more suitable as it's built into Docker and it is simple to configure. Better yet, it does not stop you running containers outside Swarm too nor running Kubernetes and Swarm side by side. It's great for testing ideas and a tool that developers should be aware of.

If you find yourself in a situation where you need to run all sorts of applications and control the cloud, **Mesosphere** may be your option. You can even run Kubernetes inside it, but then you need to know two very complex systems. However, that may be your path from legacy systems to fully containerised system, where in final step Mesosphere is deprecated leaving only Kubernetes.

**OpenShift** is an enterprise friendly PaaS that utilises Kubernetes. That may be the choice of when you want to standardise your development and deployment processes on enterprise level.
