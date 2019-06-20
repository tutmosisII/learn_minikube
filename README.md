# Aprendiendo Minikube

Es una herramienta open source que almacenada en [Github](https://github.com/kubernetes/minikube)

# Instalación v1.1.1 2019-06-07

## Instalación de virtualbox

Minikube es una máquina virtual, para poder ejecutarla necesitara el hypervisor de VirtualBox instalado primero en su máquina.
	
	Copie y pegue el siguiente comando:
        curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.1.1/minikube-linux-amd64 && chmod +x minikube && sudo cp minikube /usr/local/bin/ && rm minikube

Este comand descarga, habilita para ejecución e instala en **/usr/local/bin** minukube.

# Iniciando minukube

	minukube start

Este monando iniciará una máquina virtual de virtualbox con el cluster de kubernetes.

# Accediendo a minukube

Para usar el cluster usted necesita tener instalada la línea de comados de [kubectl](https://kubernetes.io/es/docs/tasks/tools/install-kubectl/#instalar-kubectl)
tambien puede usar el [script de instalación](scripts/install_kubectl.sh)

1) Verifique que minikue instaló las configuraciones de acceso

   cat ~/.kube/config

2) Liste los nodos presentes en el cluster

   kubectl get nodes

3) Liste los pods desplegados

   kubectl get pods
   kubectl get pods --all-namespaces
   
# Creando un primer deployment

Corremos una imagen con un nginx

1) Crear un deploymnet

   kubectl create deployment mynginx --image=nginx

2) Verifique el pod
  
   kubectl get pods

# Accediendo al servidor

Para acceder al servidor se require crear un servicio.

   kubectl expose deployment mynginx --port 80

Redireccione el puerto a su ambiente local

   kubectl port-forward svc/mynginx 8080:80

Cargue la página	

   curl localhost:8080
  

