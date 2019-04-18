
kubectl create ns jenkins
helm upgrade -i jenkins -f jenkins.yaml --namespace jenkins stable/jenkins

kubectl create ns spinnaker
kubectl create secret generic --from-file=$HOME/.kube/cluster1 cluster1-kubeconfig -n spinnaker
helm upgrade -i spinnaker -f spinnaker.yaml --namespace spinnaker --timeout 600 stable/spinnaker


# Install istion 
cd istio-1.1.2
for i in install/kubernetes/helm/istio-init/files/crd*yaml; do kubectl apply -f $i; done