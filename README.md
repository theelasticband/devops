# DevOps excercises
A prerequisite would be to know the basis for the 
## 1. Local environment setup
 Create a local Kind or MicroK8s cluster and install argocd in it
 some help can be found here
 - https://medium.com/ibm-cloud/gitops-quick-start-with-kubernetes-kind-cluster-5677f94adf69
 - https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#1-overview	
 - https://argo-cd.readthedocs.io/en/stable/getting_started/ 
Parameters:
- Use this repository as the backing repo
- create a branch for your cluster
- location cluster/<clustername>
  
# 2. The following excercise main purpose is to develop practical kubernetes/git/gitops skills
   Deploy app1 and app2 in namespace local using argocd
   The application images are published under `aandonov/app1:latest` and `aandonov/app2:latest` in dockerhub.
   The applications are only nginx, so deploy them in scale=1 and as a regular deployment in namespace `local`
# 3. Promoting the image
  - Alter the github action (to be a PR/merge when ready) to build a semver tag of the image (app1 and app2 respectively) based on the commit sha in github `stage-<vM.m.p>-<hash>`
  - After every successful merge the build config will be reset so that the next person has the chance 
  - in ArgoCD prepare a 2nd deployment in namespace `stage` of the 2 apps
  - create deployment based on the semver of the image above
# 4. Some networking fun
  - Deploy istio in the local cluster
  - mark namespace `local` for injection
  - define an ingressgateway/vsvc to both applications in `local` namespace 
# 5. Networking not so fun
  - Using argocd rollout, prepare a canary deployment for app1
# 6. Argo workflows
  To be done together
