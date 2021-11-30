No Portal Azure, criar um Kubernet Service. 
 
 az login
 az aks get-credentials --name app-k8s --resource-group app-rg

Mudar do powershell para cmd

 kubectl version --client
 kubectl get pods

-Entrar no dir bd
kubectl create -f permissoes.yaml
kubectl create -f statefulset.yaml
kubectl create -f servico-banco.yaml

-Entrar no dir app
kubectl create -f deployment.yaml
kubectl create -f servico-aplicacao.yaml

- Depois entrar no pod do mysql
kubectl exec -it statefulset-mysql-0 sh
mysql -u root

----Script do Banco -------------------------------------------------------------------------------------
use loja
create table produtos (id integer auto_increment primary key, nome varchar(255), preco decimal(10,2));
alter table produtos add column usado boolean default false;
alter table produtos add column descricao varchar(255);
create table categorias (id integer auto_increment primary key, nome varchar(255));
insert into categorias (nome) values ("Motos"), ("Carros"), ("Games"), ("Tecnologia");
alter table produtos add column categoria_id integer;
update produtos set categoria_id = 1;
---------------------------------------------------------------------------------------------------------
exit 
exit
----------------------------------------------------------------------------------------------------------

Ver se o serviço está Rodando. 
kubectl get service

Testar pelo IP

---- Sucesso 

Mikube é 1 clustes simples, so pra desenvolvimento. 


------- Persistencia
kubectl get persistentvolume
kubectl get persistentvolume pvc-dfe678db-a284-4760-adeb-468f44e80565 --output yaml


------ Storage 
kubectl get storageclass

kubectl delete  -f volumePremium.yaml

---Deletar pod
kubectl delete pods statefulset-mysql-0 --grace-period=0 --force
