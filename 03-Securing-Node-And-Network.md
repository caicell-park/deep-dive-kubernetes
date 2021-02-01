# Securing Node And Network Option and Object

1. Using the node’s default Linux namespaces in pods
    - spec.hostNetwork
    - spec.containers.ports.containerPort and spec.containers.ports.hostPort
    - spec.hostPID and spec.hostIPC

2. SecurityContext
- Running containers as different users 
    - spec.securityContext.runAsUser and spec.securityContext.runAsNonRoot
- Allocate the all permission of kernel like a root user
    - spec.securityContext.privileged
- Adding or dropping a container’s kernel capabilities
    - spec.securityContext.capabilities.add
    - spec.securityContext.capabilities.drop
    - spec.securityContext.readOnlyRootFilesystem
- Assign the permission to the mounted directory
    - spec.securityContext.fsGroup and spec.securityContext.supplementalGroups

3. Defining security policies to limit what pods can do 

- What: Assign below functionalities to PodSecurityPolicy

```
Whether a pod can use the host’s IPC, PID, or Network namespaces
Which host ports a pod can bind to
What user IDs a container can run as
Whether a pod with privileged containers can be created
Which kernel capabilities are allowed, which are added by default and which are always dropped
What SELinux labels a container can use
Whether a container can use a writable root filesystem or not
Which filesystem groups the container can run as
Which volume types a pod can use
```

- How to apply a specific account, RBAC: Attach a PodSecurityPolicy to ClusterRole. ClusterRole is injected to many users or service accounts. 


4. Securing the pod network

# Reference
[Kubernetes in Action, Chapter 12. Securing cluster nodes and the network](https://learning.oreilly.com/library/view/kubernetes-in-action/9781617293726/Text/13.html)
