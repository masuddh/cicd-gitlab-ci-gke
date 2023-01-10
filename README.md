CI/CD Using Gitlab CI and deploy to GKE (Google Kubernetes Engine)

The following is an explanation of the CICD that I have made :

- Here I made 2 simple applications using go and nodejs in a mono repo. more details are here --> https://gitlab.com/masuddhh/monorepo-ci
- Then in the root directory of the repo I created a gitlab ci file to trigger the deploy project in the mono repo
- in each apps, also given a gitlab ci file to trigger deployment
- for build apps, I use Docker on shared gitlab runner from Gitlab
- for registry, I use Gitlab Container Registry 
![image](https://user-images.githubusercontent.com/59553495/198093567-b3685ac8-0fac-4b75-872a-1bb3f3b8d895.png)
- for deployment, there are some pre-requisites that must be prepared, such as service account with role Kubernetes Engine Admin to connect the cluster, then store in variabels cicd gitlab
![image](https://user-images.githubusercontent.com/59553495/198094835-d68d4079-9b49-4f88-971e-071dab9e6ed6.png)
- for manifest kubernetes i just use deployment, service, and ingress because that is simple apps

Finally this is the result of exposing the kubernetes service
- Deployment 
![image](https://user-images.githubusercontent.com/59553495/198097325-25e603e7-16ab-4d42-813d-660228194e45.png)

- Service
![image](https://user-images.githubusercontent.com/59553495/198096933-2f524a16-cb51-4f0c-b4c6-b93078552b19.png)




reference: 
- https://github.com/masterful/nodejs-hello-world
- https://blog.devgenius.io/go-docker-hello-world-f092ecf7cead
- https://blog.searce.com/gitlab-ci-cd-to-deploy-applications-on-gke-using-shared-runner-47f8c42817ac
