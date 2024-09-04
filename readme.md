### Kubernetes Sandbox on Kind
https://kind.sigs.k8s.io/docs/user/quick-start/ 

[Kind cheat sheet](https://www.hackingnote.com/en/cheatsheets/kind/)

- Create cluster 
```
$ kind create cluster --name ccdaniele-kind --config /multi-node.yaml
```
- To create a cluster with multiple nodes you should update the **kind:cluster** object with command below: 

```
$ cat <<EOF | kind create cluster --name local --config -
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
EOF
```
or by setting your own file with configurations: 
```
kind create cluster --config <path to your file>
```
### **kind** command flags: 

```

Usage:
  kind [command]

Available Commands:
  build       Build one of [node-image]
  completion  Output shell completion code for the specified shell (bash, zsh or fish)
  create      Creates one of [cluster]
  delete      Deletes one of [cluster]
  export      Exports one of [kubeconfig, logs]
  get         Gets one of [clusters, nodes, kubeconfig]
  help        Help about any command
  load        Loads images into nodes
  version     Prints the kind CLI version

Flags:
  -h, --help              help for kind
      --loglevel string   DEPRECATED: see -v instead
  -q, --quiet             silence all stderr output
  -v, --verbosity int32   info log verbosity, higher value produces more output
      --version           version for kind
```



### kind create flags: 

```
 --help   help for create
Usage:                                                                          Global Flags:
  kind create [flags]                                                                 --loglevel string   DEPRECATED: see -v instead
  kind create [command]                                                           -q, --quiet             silence all stderr output
Available Commands:                                                               -v, --verbosity int32   info log verbosity, higher value produces more output
  cluster     Creates a local Kubernetes cluster                                Use "kind create [command] --help" for more information about a command.
```

https://github.com/kubernetes/dashboard 

https://medium.com/@munza/local-kubernetes-with-kind-helm-dashboard-41152e4b3b3d

https://github.com/GridGain-Demos/ignite-kubernetes-essentials-training?tab=readme-ov-file

kubectl proxy port=8001

--add-exports=java.base/jdk.internal.misc=ALL-UNNAMED
--add-exports=java.base/sun.nio.ch=ALL-UNNAMED
