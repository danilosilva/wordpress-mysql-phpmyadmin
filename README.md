
Para subir a stack realizar os procedimentos abaixo:
Foram criados tres databases com os nomes db_app1, db_app2 e db_app2. Cada database tem um usuario user/pass

Requisitos: Para manter os dados mesmo que os pods reiniciem, foram criados pvs do tipo hostpath. é necessário criar os diretorios abaixo no worker que hospedará os containers:

/mnt/sistema/app01

/mnt/sistema/app02

/mnt/sistema/app03

/mnt/sistema/db01

##Criando banco de dados

kubectl apply -f namespaces/db.yaml

kubectl apply -f secrets/db.yaml

kubectl apply -f pvs/db.yaml

kubectl apply -f deployments/db.yaml

kubectl apply -f services/db.yaml

##Criando ambiente phpmyadmin

kubectl apply -f namespaces/phpmyadmin.yaml

kubectl apply -f secrets/phpmyadmin.yaml

kubectl apply -f deployments/phpmyadmin.yaml

kubectl apply -f services/phpmyadmin.yaml

##Criando ambiente aplicacao1

kubectl apply -f namespaces/app1.yaml

kubectl apply -f secrets/app1.yaml

kubectl apply -f pvs/app1.yaml

kubectl apply -f deployments/app1.yaml

kubectl apply -f services/app1.yaml

##Criando ambiente aplicacao2

kubectl apply -f namespaces/app2.yaml

kubectl apply -f secrets/app2.yaml

kubectl apply -f pvs/app2.yaml

kubectl apply -f deployments/app2.yaml

kubectl apply -f services/app2.yaml

##Criando ambiente aplicacao3

kubectl apply -f namespaces/app3.yaml

kubectl apply -f secrets/app3.yaml

kubectl apply -f pvs/app3.yaml

kubectl apply -f deployments/app3.yaml

kubectl apply -f services/app3.yaml
