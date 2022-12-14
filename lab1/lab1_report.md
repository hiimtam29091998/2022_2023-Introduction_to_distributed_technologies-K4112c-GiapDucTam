University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4112c
Author: Giap Duc Tam
Lab: Lab1
Date of create: 14.12.2022
Date of finished: 14.12.2022

Answers of questions:
1. Что сейчас произошло и что сделали команды указанные ранее?
- We can access to vault via link: http://localhost:8200
- minikube start: `Starting minikube`
- kubectl apply -f C:\Users\Giap Tam\Desktop\desk\introduction\mymanifest.yaml: `Applying the configuration of manifest to create pod`
- kubectl get pods (Optional): `List all pods that minikube has`
- minikube kubectl -- expose pod vault --type=NodePort --port=8200: `Exposing to create new service NodePort type with port 8200`
- kubectl port-forward service/vault 8200:8200: `Getting to container on port 8200`
- minikube stop: `Stopping minikube`

2. Где взять токен для входа в Vault?
- Using command "kubectl logs vault" then find root token in logs.<br><br>
![schema_lab1 drawio](https://user-images.githubusercontent.com/83900905/192099613-bd190993-6d22-4617-a061-63f447f61b27.png)
<br>Schema 1 - Nodeport working <br><br>
![Capture](https://user-images.githubusercontent.com/83900905/194343990-a2487e52-7c62-4171-874b-d753c92b7c15.JPG)
Picture 1 - Loggin page using token on vault
