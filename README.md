
kubectl create ns jenkins
helm upgrade -i jenkins -f jenkins.yaml --namespace jenkins stable/jenkins

kubectl create ns spinnaker

helm upgrade -i spinnaker -f spinnaker.yaml --namespace spinnaker --timeout 1200 stable/spinnaker