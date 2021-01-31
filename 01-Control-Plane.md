# Control Plane
 
Control Plane is a coordinator of Kubernetes Cluster. Control Plane provides the following components:
 
```
Component / Role
API server / Public Channel
ETCD, distributed persistent storage / Note Recording State of Object
Scheduler / Resource Distributor
Controller Manager / Each Department Manager
```
 
Let me give the short story for the above components:
 
A company is composed of many departments. All department consider own profit and their role. How they communicate with each other? They usually had two channels, public and private.
 
API server is a public channel. Via the public channel, they share the piece of information to manage and operate their role. The public channel provides not only the communication tunnel and but also answers to questions from a department. ETCD is a place to store any information of the company, Kubernetes Cluster.
 
Controller Manager is a manager of each department. Controller Manager asks and requests its requirements to the public channel, API server. Scheduler is a resource team to distribute the company's resources when Controller Manager requests resources to API Server.
 
 
## Reference
Kubernetes in Action Chapter 11. Kubernetes in Action
