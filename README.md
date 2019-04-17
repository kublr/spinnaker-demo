
kubectl create ns jenkins
helm upgrade -i jenkins -f jenkins.yaml --namespace jenkins stable/jenkins

kubectl create ns spinnaker
kubectl create secret generic --from-file=$HOME/.kube/cluster1 cluster1-kubeconfig -n spinnaker
helm upgrade -i spinnaker -f spinnaker.yaml --namespace spinnaker --timeout 1200 stable/spinnaker