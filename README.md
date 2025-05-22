# GitOps / Flux

Gitops Kubernetes Workshop

Prerequisites
APPS

Lens https://k8slens.dev/download
Github Desktop https://desktop.github.com/download/
K9s https://k9scli.io/topics/install/
Flux https://fluxcd.io/flux/installation/
VScodium/Vscode https://code.visualstudio.com/download

GITHUB
Github account aanmaken https://github.com/signup
Maak Github API key (Personal Access Token) https://github.com/settings/tokens
Noteer de PAT

CLUSTER
CYSO Cloud Managed Kubernetes cluster met minimaal 3 nodes aanmaken

Noteer shoot domain naam uit het my.fuga.cloud -> EMK -> EMK Cluster -> “clusternmaam”  -> overview tabblad

Zet de DNS extensie aan in je cluster.  my.fuga.cloud -> EMK -> EMK Cluster -> “clusternmaam” -> YAML tabblad
	
	Voeg toe aan de shoot yaml definitie



kind: Shoot
spec:
  extensions:
    - type: shoot-dns-service




Laat alle bestaande gegevens staan en druk op “save”, na enkele minuten is jouw cluster weer healthty (overview status / all green”

Toegang tot kubernetes 
Login op https://my.fuga.cloud -> EMK -> EMK Clusters -> Cluster -> Access
Download kubeconfig via Request a Kubeconfig met een geldigheid van 1 dag




## Sample deploy

> export GITHUB_TOKEN=XXXXXX  
> export GITHUB_USER=<USERNAME>  
> flux bootstrap github --owner=$GITHUB_USER --repository=gitops-workshop --branch=main --path=./clusters/my-cluster --components-extra=image-reflector-controller,image-automation-controller --personal  
