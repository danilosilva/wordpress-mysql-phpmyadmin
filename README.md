# Rock Stage SRE Assessment

## About Rock Stage

Para subir a stack realizar os procedimentos abaixo:
Foram criados tres databases com os nomes db_app1, db_app2 e db_app2. Cada database tem um usuario user/pass como dono conforme tabela abaixo:

DB      | user | pass |
db_app1 | app1 | app1 |
db_app2 | app2 | app2 |
db_app2 | app3 | app3 |

Requisitos: Para manter os dados mesmo que os pods reiniciem, foram criados pvs do tipo hostpath. é necessário criar os diretorios abaixo no worker que hospedará os containers:

/mnt/sistema/app01
/mnt/sistema/app02
/mnt/sistema/app03
/mnt/sistema/db01

--  Criando banco de dados

## Namespace
kubectl apply -f namespaces/db.yaml

## Secret com as senhas de root e dos usuarios das aplicações
kubectl apply -f secrets/db.yaml

## Criando pv e pvs
kubectl apply -f pvs/db.yaml

## Deployment
kubectl apply -f deployments/db.yaml

## Service
kubectl apply -f services/db.yaml

-- Criando ambiente phpmyadmin
## NameSpace
kubectl apply -f namespaces/phpmyadmin.yaml

## Secret com a senha de root 
kubectl apply -f secrets/phpmyadmin.yaml

## Deployment
kubectl apply -f deployments/phpmyadmin.yaml

# Service ( esse servico é do tipo NodePort e foi configurado a porta 30083 para acesso)
# Ex: http:IP_MINIKUBE:30083
kubectl apply -f services/phpmyadmin.yaml

-- Criando ambiente aplicacao1
## NameSpace
kubectl apply -f namespaces/app1.yaml

## Secret com a senha do usuario app1
kubectl apply -f secrets/app1.yaml

## Criando pv e pvs
kubectl apply -f pvs/app1.yaml

## Deployment
kubectl apply -f deployments/app1.yaml

# Service ( esse servico é do tipo NodePort e foi configurado a porta 30080 para acesso)
# Ex: http:IP_MINIKUBE:30080
kubectl apply -f services/app1.yaml

-- Criando ambiente aplicacao2
## NameSpace
kubectl apply -f namespaces/app2.yaml

## Secret com a senha do usuario app2
kubectl apply -f secrets/app2.yaml

## Criando pv e pvs
kubectl apply -f pvs/app2.yaml

## Deployment
kubectl apply -f deployments/app2.yaml

# Service ( esse servico é do tipo NodePort e foi configurado a porta 30081 para acesso)
# Ex: http:IP_MINIKUBE:30081
kubectl apply -f services/app2.yaml


-- Criando ambiente aplicacao3
## NameSpace
kubectl apply -f namespaces/app3.yaml

## Secret com a senha do usuario app3
kubectl apply -f secrets/app3.yaml

## Criando pv e pvs
kubectl apply -f pvs/app3.yaml

## Deployment
kubectl apply -f deployments/app3.yaml

# Service ( esse servico é do tipo NodePort e foi configurado a porta 30082 para acesso)
# Ex: http:IP_MINIKUBE:30082
kubectl apply -f services/app3.yaml
