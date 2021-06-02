### Create halm 
helm create hello-helm-config
### change will be in values.yaml:
image:
  repository: hello-helm
  pullPolicy: IfNotPresent
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

 
 
