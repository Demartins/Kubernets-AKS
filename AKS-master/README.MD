# Apresentação Kubernetes com Azure AKS

Primeiramente precisamos logar no Portal Azure com uma conta. 
Logo após criar um Kubernet Service. 
 
## az login
## az aks get-credentials --name app-k8s --resource-group app-rg

Mudar do powershell para cmd

 ### kubectl get pods

- Entrar no dir /bd
## kubectl create -f permissoes.yaml
## kubectl create -f statefulset.yaml
## kubectl create -f servico-banco.yaml

- Entrar no dir /app
## kubectl create -f deployment.yaml
## kubectl create -f servico-aplicacao.yaml

- Depois entrar no pod do mysql
## kubectl exec -it statefulset-mysql-0 sh
## mysql -u root

### executar o **script-bd.sql** dentro do container
### exit e exit
-----------------------------------------------------

Ver se o serviço está Rodando. 

## kubectl get service

Testar pelo aplicação pelo IP no Browser
Exemplo: http://20.81.62.106/ 


# Agora Vamos escalar a nossa aplicação.

add 3 ou mais replicas no deployment.

## kubectl apply -f deployment.yaml

