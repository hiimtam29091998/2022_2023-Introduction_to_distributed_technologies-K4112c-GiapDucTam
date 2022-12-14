University: [ITMO University](https://itmo.ru/ru/)<br>
Faculty: [FICT](https://fict.itmo.ru)<br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)<br>
Year: 2022/2023<br>
Group: K4112c<br>
Author: Giap Duc Tam<br>
Lab: Lab2<br>
Date of create: 14.12.2022<br>
Date of finished: 14.12.2022<br>
Creating a deployment with manifest name webserver.yaml.: kubectl create -f C:\Users\GIAP TAM\Desktop\desk\introduction\lab2\webserver.yaml<br>
In this file, define the environment values with keys: REACT_APP_USERNAME and REACT_APP_COMPANY_NAME. This deployment has 3 replicasets. <br>
Then, creating a service with type `NodePort`and port is container port in the webserver manifest: kubectl create -f C:\Users\GIAP TAM\Desktop\desk\introduction\lab2\webserver-svc.yaml<br>
After that, we can access to website via localhost port 3000 and values for key that we defined in env appeared:<br>
![1]<br>
Pictrue 1 - Result after deploy
