Kubernetes -Foundations
www.linkedin.com/in/ujjwal-gupta-409665167
Container
 ↓
Runs the actual application
Pod
 ↓
A box that contains one or more containers.
Kubernetes manages Pods, not containers.
ReplicaSet
 ↓
Keeps the required number of Pods alive.
Deployment
 ↓
Defines the desired state.
Creates and manages ReplicaSets.
kubectl apply
 ↓
Sends the desired state (YAML) to Kubernetes.
Kubernetes
 ↓
Compares:
Current State
vs
Desired State
Then changes only what is necessary.
