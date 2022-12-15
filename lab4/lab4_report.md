University: [ITMO University](https://itmo.ru/ru/)<br>
Faculty: [FICT](https://fict.itmo.ru)<br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)<br>
Year: 2022/2023<br>
Group: K4112c<br>
Author: Giap Duc Tam<br>
Lab: Lab4<br>
Date of create: 15.12.2022<br>
Date of finished: 15.12.2022<br>
Working process:<br>
1. Start CNI calico with Multi-node Cluster (2 node): `minikube start --network-plugin=cni --cni=calico`
2. Adding an worker node: `minikube node add`
3. Check calico working: `kubectl get pods -l k8s-app=calico-node -A` (Pic 1)
![1-check-calico-work](https://user-images.githubusercontent.com/83900905/195160131-58c188d9-19b2-4d7e-9ec9-4e21c853e50b.JPG)<br>
Pic 1 - Checking calico nodes works
4. Label 2 nodes with zone-label:  `kubectl label nodes minikube zone=west` and `kubectl label nodes minikube-02 zone=east`
5. Create ippool with 2 labels in step 4: `kubectl create -f "C:\Users\GIAP TAM\Desktop\introduction\lab4\ip.yaml"`
6. Create deployment with 2 replicaset and env: `kubectl create -f "C:\Users\GIAP TAM\Desktop\introduction\lab4\replicaset.yaml"`
7. Ceate service for deployment: `kubectl create -f "C:\Users\GIAP TAM\Desktop\introduction\lab4\svc.yaml"`
8. Forward it to port. Result in Pic 2: `kubectl port-forward service/web-service 3000:3000`
![lab4](https://user-images.githubusercontent.com/104643246/207835070-c76da804-d2e7-4949-bde1-f10352d2222b.png)<br>
Pic 2 - Result on browser (IP address is same with ippool config file)
9. Ping check from this pod to that pod using kubectl exec: `kubectl exec -it webserver-b74d57f96-5hb2s -- ping 192.168.66.0`
![3-ping](https://user-images.githubusercontent.com/83900905/195160550-69b62ce8-470d-47e8-8578-f9e41a0f7125.JPG)<br>
Pic 3 - Successfully ping from pod to other pod
