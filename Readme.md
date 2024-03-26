# Requirements

- Kubectl
    - Windows: https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
    - Linux: https://kubernetes.io/docs/tasks/tools/install-kubectl/
- Helm
    - Windows: https://helm.sh/docs/intro/install/#windows
    - Linux: https://helm.sh/docs/intro/install/#linux
- Docker
    - docker Windows: https://docs.docker.com/get-docker/
    - docker Linux: https://docs.docker.com/get-docker/
- KinD
    - https://kubernetes.io/docs/tasks/tools/

# Steps
# Create a kubernetes cluster of 1 control plane and 3 worker nodes
`kind create cluster --name my-cluster --config my-cluster.yaml`

# Check the cluster info
`kubectl cluster-info`

# Check the nodes with kubectl
`kubectl get nodes -o wide`
