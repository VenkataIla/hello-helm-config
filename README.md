### Create halm 
helm create hello-helm-config
### change will be in values.yaml:
image:
  repository: hello-helm
  pullPolicy: IfNotPresent
  # Overrides the image tag whose default is the chart appVersion.
  tag: ""
###  /templates/deployment.yaml set the appropriate port:
 ports:
    - name: http
      containerPort: 8080
      protocol: TCP
 ### Push charts to cluster 
 helm install hello-helm-config --debug --dry-run hello-helm-config
 ### check the chart
 helm list -a
 ### gradle build 
 gradle k8s:resource k8s:helm -Pkubernetes
 ### get service 
 minikube service hello-helm
 
 
 
