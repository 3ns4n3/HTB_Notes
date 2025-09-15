Kubernetes is a container orchestration system, which functions by running all applications in containers isolated from the host system through multiple layers of protection. 
This approach ensures that applications are not affected by changes in the host system, such as updates or security patches. 
The K8s architecture comprises a master node and worker nodes, each with specific roles.
Service 	TCP Ports
etcd 	2379, 2380
API server 	6443
Scheduler 	10251
Controller Manager 	10252
Kubelet API 	10250
Read-Only Kubelet API 	10255

K8's Security Measures

Kubernetes security can be divided into several domains:

    Cluster infrastructure security
    Cluster configuration security
    Application security
    Data security

Each domain includes multiple layers and elements that must be secured and managed appropriately by the developers and administrator
**KUBERNETES API**
Request 	Description
GET 	Retrieves information about a resource or a list of resources.
POST 	Creates a new resource.
PUT 	Updates an existing resource.
PATCH 	Applies partial updates to a resource.
DELETE 	Removes a resource.

**Exctracting Kubernetes PODS**
cry0l1t3@k8:~$ kubeletctl -i --server 10.129.10.11 pods

┌────────────────────────────────────────────────────────────────────────────────┐
│                                Pods from Kubelet                               │
├───┬────────────────────────────────────┬─────────────┬─────────────────────────┤
│   │ POD                                │ NAMESPACE   │ CONTAINERS              │
├───┼────────────────────────────────────┼─────────────┼─────────────────────────┤
│ 1 │ coredns-78fcd69978-zbwf9           │ kube-system │ coredns                 │
│   │                                    │             │                         │
├───┼────────────────────────────────────┼─────────────┼─────────────────────────┤
│ 2 │ nginx                              │ default     │ nginx                   │
│   │                                    │             │                         │
├───┼────────────────────────────────────┼─────────────┼─────────────────────────┤
│ 3 │ etcd-steamcloud                    │ kube-system │ etcd                    │
│   │                                    │             │                         │
├───┼────────────────────────────────────┼─────────────┼─────────────────────────┤

To effectively interact with pods within the Kubernetes environment, it's important to have a clear understanding of the available commands. 
One approach that can be particularly useful is utilizing the scan rce command in kubeletctl. 
This command provides valuable insights and allows for efficient management of pods.
