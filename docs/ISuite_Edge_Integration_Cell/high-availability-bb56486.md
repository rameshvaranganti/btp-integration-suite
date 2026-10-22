<!-- loiobb564867c7dd45b495e21c0a4c1d1a39 -->

# High Availability

High Availability \(HA\) is a key requirement for production environments. In a nutshell, HA aims to minimize downtime of a system or service.

Kubernetes as a platform offers a number of resiliency features, like restarting failed containers, removing containers that don't respond to defined health checks, already improving availability to a certain level. Additionally, it can take care of scaling and failover of applications, or handle node failures gracefully.





### Edge Integration Cell Kubernetes Cluster Topology

Basic Kubernetes cluster setup for HA:

-   Three control plane nodes handled implicitly on managed K8s platforms \(Azure AKS, Amazon EKS\)

-   Three worker nodes

You can enable HA mode for an Edge Node, during onboarding, see [Add an Edge Node](add-an-edge-node-d96772f.md).



### Multiple Availability Zones \(Multi-AZ\)

An availability zone is an isolated failure domain within a data center infrastructure, typically with independent power, cooling, and networking. Cloud platforms provide multiple availability zones out of the box for Kubernetes deployments. You can enable multi-availability zone support on any Kubernetes deployment as long as the underlying infrastructure supports multiple availability zones.

For a high availability setup with Edge Integration Cell, you need at least three worker nodes distributed across three availability zones.



### Auto-Scaling

Scalability and reliability are key features of Kubernetes. Horizontal Pod Autoscaler \(HPA\) is a standard K8s feature provided by the core. For Edge Integration Cell, we'll gradually support auto-scaling for selected components.

> ### Note:  
> HPA is using the Metrics API which is provided by the Metrics Server. Make sure that a Metrics Server is deployed on your K8s cluster. For example, on Amazon EKS, a Metrics Server is not deployed by default.

