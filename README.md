1- How many ConfigMaps exist in the environment? 
<img width="653" alt="1" src="https://github.com/user-attachments/assets/a0f9e394-a9a5-4b8d-b881-409fd6b7ba1e">

2- Create a new ConfigMap Use the spec given below. ConfigName Name: webapp-config-map Data: APP_COLOR=darkblue 
<img width="653" alt="2 1" src="https://github.com/user-attachments/assets/80b5683c-31ee-4d3e-97fd-9a2e07affbb3">
<img width="653" alt="2 2" src="https://github.com/user-attachments/assets/269357cc-3846-4c19-ba36-66a46430120d">

3- Create a webapp-color POD with nginx image and use the created ConfigMap 
<img width="656" alt="3 1" src="https://github.com/user-attachments/assets/db706649-b170-4893-b44d-4ff545ae7cce">
<img width="656" alt="3 2" src="https://github.com/user-attachments/assets/4967d1e2-a201-4d1e-8600-ced1a8be90a6">

 4- How many Secrets exist on the system?
 
 <img width="650" alt="4" src="https://github.com/user-attachments/assets/3842dcca-7aeb-4b70-9678-7aa4b46fbbc0">

6- create a POD called db-pod with the image mysql:5.7 then check the
 POD status
 <img width="656" alt="6 1" src="https://github.com/user-attachments/assets/a3ce4a54-de08-4d96-9851-9a605afb07f9">
<img width="662" alt="6 2" src="https://github.com/user-attachments/assets/6f1823a1-e216-49e9-aa9c-2aadc901a31d">

 7- why the db-pod status not ready?
 
because I need to specify the environment variables

 8- Create a new secret named db-secret with the data given below.
 Secret Name: db-secret
 Secret 1: MYSQL_DATABASE=sql01
 Secret 2: MYSQL_USER=user1
 Secret3: MYSQL_PASSWORD=password
 Secret 4: MYSQL_ROOT_PASSWORD=password123
 <img width="656" alt="7 1" src="https://github.com/user-attachments/assets/3ecc5c95-dffb-44a5-a668-ba39c9fbcf7f">
<img width="658" alt="7 2" src="https://github.com/user-attachments/assets/281a2cd8-18ec-4b5d-9b64-33409b733f55">

 9- Configure db-pod to load environment variables from the newly created
 secret.
 Delete and recreate the pod if required.
 <img width="658" alt="8 1" src="https://github.com/user-attachments/assets/97d33c64-a97b-4676-a689-c14ffb22a6fc">
<img width="656" alt="8 2" src="https://github.com/user-attachments/assets/5d5fb04c-8faf-479c-a2ae-e07f43fc78cf">

10- Create a multi-container pod with 2 containers.
 Name: yellow
 Container 1 Name: lemon
 Container 1 Image: busybox
 Container 2 Name: gold
 Container 2 Image: redis
 
<img width="656" alt="10 1" src="https://github.com/user-attachments/assets/1dd19583-b94e-402f-9ae4-2049628eb1bf">
<img width="657" alt="10 2" src="https://github.com/user-attachments/assets/a793e3bb-750d-46d3-b363-b901e92ccf82">

11- Create a pod red with redis image and use an initContainer that
 uses the busybox image and sleeps for 20 seconds
 <img width="662" alt="11 1" src="https://github.com/user-attachments/assets/1c4ac568-68b3-424d-8ba9-27d41264df77">
<img width="657" alt="11 2" src="https://github.com/user-attachments/assets/50a35f7f-434d-4aa9-b51c-51439427a68b">

12- Create a pod named print-envars-greeting.
 1. Configure spec as, the container name should be
 print-env-container and use bash image.
 2. Create three environment variables:
 a. GREETING and its value should be “Welcome to”
 b. COMPANY and its value should be “DevOps”
c. GROUP and its value should be “Industries”
 4. Use command to echo ["$(GREETING) $(COMPANY) $(GROUP)"]
 message.
 5. You can check the output using <kubctl logs -f [ pod-name ]>
 command.
<img width="656" alt="12 1" src="https://github.com/user-attachments/assets/f2be6a14-9854-4e8f-ab11-ea3215200fac">
<img width="659" alt="12 2" src="https://github.com/user-attachments/assets/58b5d48a-450c-4305-bae5-4a7bd8ae3aa3">

16- Create a Persistent Volume with the given specification.
 Volume Name: pv-log
 Storage: 100Mi
 Access Modes: ReadWriteMany
 Host Path: /pv/log
 
<img width="652" alt="16 1" src="https://github.com/user-attachments/assets/b38f7817-769c-4936-be38-20bb2b0d383d">
<img width="655" alt="16 2" src="https://github.com/user-attachments/assets/e3fb0232-4cd4-42b3-8684-885434eaae22">

17- Create a Persistent Volume Claim with the given specification.
 Volume Name: claim-log-1
 Storage Request: 50Mi
 Access Modes: ReadWriteMany
 <img width="653" alt="17 1" src="https://github.com/user-attachments/assets/447d0c1a-afc7-42bd-80af-47cfb66cce0b">
<img width="659" alt="17 2" src="https://github.com/user-attachments/assets/9cb2e04c-7d40-4a12-9fe2-f142132936f6">

18- Create a webapp pod to use the persistent volume claim as its storage.
 Name: webapp
 Image Name: nginx
 Volume: PersistentVolumeClaim=claim-log-1
 Volume Mount: /var/log/nginx
 <img width="659" alt="18 1" src="https://github.com/user-attachments/assets/4005ca43-8812-40e1-a9d7-e3646a75ac06">
<img width="656" alt="image" src="https://github.com/user-attachments/assets/a9099dd8-f1d7-4b0e-9d7c-37f9282db4e3">
