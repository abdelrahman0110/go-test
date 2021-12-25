we create a multistage Dockerfile in directory docker to containerized a golang server
and build the server by RUN command inside Dockerfile

go build -o main main.go

then create a multistage dockerfile to copy a executable file

for reduce a image size

then push image in docker hub its name "abdelrhman0110/go-test:latest"

to access the image from kubernetes


we create a yaml file for kubernetes deployment :

kubectl create deployment (name of deployment) --image=abdelrhman0110/go-test:latest --replicas=3 --dry-run=client -o yaml > go_deployment.yaml

and fill go_deployment.yaml file with probes and container port,
then create a nodePort service in same file to access server.
to apply the yaml file

kubectl apply -f go_deployment.yaml


we create helm chart by command :

helm create (chart name)

we edit files inside the chart and values,
to apply the chart we created:

helm install (release name) (chart name)
