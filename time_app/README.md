Sample App

Sample Python Flask application to showcase the steps of building and running a web server with Docker.

Docker: https://www.docker.com/
Flask documentation: https://flask.palletsprojects.com/en/1.1.x/

## docker
docker build -t yaoxinliu/sample-time-app:latest .

docker run --name sample-time-app -p 8080:8080 -it yaoxinliu/sample-time-app:latest

http://localhost:8080/time

docker login

docker push yaoxinliu/sample-time-app:latest

## minikube

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-arm64

sudo install minikube-darwin-arm64 /usr/local/bin/minikube

minikube start

minikube kubectl -- get pods -A

alias kubectl="minikube kubectl --"

kubectl create deployment sample-time-app --image=yaoxinliu/sample-time-app:latest

kubectl expose deployment sample-time-app --type="NodePort" --port 8080

kubectl get services

kubectl port-forward --address="0.0.0.0" service/sample-time-app 8080:8080

http://localhost:8080/time
