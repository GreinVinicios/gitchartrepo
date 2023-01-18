# Welcome!

This repo aims to guide you to create your own helm chart public repository.
To create a new helm repository follow the instructions below:

- Download and install the required tools¹
> Be sure that git, helm and Kubernetes cluster are up and running
- Create an empty repo on your github (e.g. *gitchartrepo*)
- In an empty folder type the following commands:
```bash
# Clonning and getting into the clonned folder
git clone <your_repo_here>
cd <your_cloned_folder_here>

# Helm commands
helm create demochart # Create an default chart based on nginx
helm package demochart # Create a package for the chart
helm repo index . # Index the chart to allow be a repository 

# Git commands
git add .
git commit -m "Initial commit"
git push
```

- Go to the created github repo.
	- Select **settings > pages**
	- On **Branch** section, select your pushed branch (e.g. *main*) and save the changes

- Take a note of the create URL (e.g.: https://greinvinicios.github.io/gitchartrepo/)
- Add the repo and install the chart:
```bash
helm repo add gitrepo https://greinvinicios.github.io/gitchartrepo/
helm install gitapp gitrepo/demochart
```
- Check the pods:
```bash
kubectl get pods
```



## Required tools
- [Helm](https://helm.sh/docs/intro/install/#from-script)
- [Git](https://github.com/git-guides/install-git#install-git-on-linux)
- Kubernetes*:
	- [k3d](https://k3d.io/v5.4.6/#install-script)
* Kubernetes is necessary to test your charts. It's possible to use k3d, minikube or even a cluster Kubernetes itself.