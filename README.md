#Aprendiendo Minikube

Es una herramienta open source que almacenada en [Github](https://github.com/kubernetes/minikube)

#Instalación v1.1.1 2019-06-07

## Instalación de virtualbox

Minikube es una máquina virtual, para poder ejecutarla necesitara el hypervisor de VirtualBox instalado primero en su máquina.
	
	Copie y pegue el siguiente comando:
        curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.1.1/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube

Este comand descarga, habilita para ejecución e instala en **/usr/local/bin** minukube.

# Iniciando minukube

	minukube start

Este monando iniciará una máquina virtual de virtualbox con el cluster de kubernetes.

# Accediendo a minukube

Para usar el cluster usted necesita tener instalada la línea de comados de kubectl

1) Verifique que minikue instaló las configuraciones de acceso

   cat ~/.kube/config

2) Liste los nodos presentes en el cluster

   kubectl get nodes

3) Liste los pods desplegados

   kubectl get pods
   kubectl get pods --all-namespaces
   
