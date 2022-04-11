# k8sTraining

 1  sudo apt-get update
    2  sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release
    3  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    4  sudo apt-get update
    5  sudo apt-get install docker-ce docker-ce-cli containerd.io
    6  sudo docker run hello-world
    7  sudo usermod -a -G docker ubuntu
    8  docker search ubuntu
    9  docker pull ubuntu
   10  docker image ls
   11  docker container --help
   12  docker container run --help
   13  docker container run ubuntu
   14  docker conatiner ls
   15  docker container ls
   16  clear
   17  docker container run -d --name sonam-nginx -p 8080:80 -it nginx
   18  docker container ls
   19  docker container ls -a
   20  docker container stop 4cd
   21  docker container ls -a
   22  docker container ls
   23  docker container start 4cd
   24  docker container ls
   25  docker exec -it sonam-nginx bash // for a running container "exec" command , for a new container "run" command
   26  docker logs 4cd
   27  docker container inspect 4cd
   28  docker container stats 4cd
   29  docker container top 4cd
   
   
  176  kubectl create namespace project1
  177  kubectl create -f pod3.yml --namespace=project1
  178  kubectl get pod
  179  kubectl get ns
  180  kubectl get pod --namespace=project1
  181  kubectl get pod --namespace=kube-system
  182  kubectl get all
  
openssl genrsa -out user1.key 2048

sudo openssl req -new -key user1.key -out user1.csr -subj "/CN=user1/O=group1"

openssl x509 -req -in user1.csr -CA ~/.minikube/ca.crt -CAkey ~/.minikube/ca.key -CAcreateserial -out user1.crt -days 500

320  kubectl config set-credentials user1 --client-certificate=user1.crt --client-key=user1.key

  321  kubectl config set-context user1-context --cluster=minikube --user=user1

  322  kubectl config view

  323  kubectl config use-context user1-context

  324  kubectl config current-context
