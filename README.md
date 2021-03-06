# mongodb-kubernetes
## Mongodb cluster with kubernetes in digitalocean(Ubuntu)
prerequisites needed:
- [doctl](https://docs.digitalocean.com/reference/doctl/how-to/install/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

### task1
- Create kubernetes cluster in your project segment in digitalocean.
- choose 
-- datacenter:bangalore
-- nodeplan: $10/month per node
-- node count: 1
and others as default
![kubernetes selection in digital ocean](images/t1.jpeg)

![setting the nodes1](images/t2.png)
![setting the nodes2](images/t3.png)
![setting the nodes3](images/t4.png)

### task2
- After node Creation,scroll down and press "Overview"
- press "Get started!"
- In "connecting to kubernetes" , copy the command and paste it in terminal of the linux.

![get started](images/t5.png)
![doctl code in terminal](images/t6.png)

### task3
- files have been created already for deployment
- change the credentials in mongodb-secrets.yaml of your own with base64 encoder!
- press right click on mouse and click "open in terminal", there copy this codes
```sh
kubectl apply -f .
```
- then check that mongo is implemented by
```sh
kubectl get all
```
![apply and getall](images/t7.png)
- After mongo is setup:
```sh
kubectl exec deployment/mongo-client -it -- /bin/bash
```
- after this then just put your credentials.
```sh
mongo --host mongo-nodeport-svc --port 27017 -u #username -p #password
```
replace #username/#password with your credentials.

if this doesn't work. then copy below code and paaste it.
```sh
mongodb
```

## Successfully completed the task!
credits:[arpan](https://www.youtube.com/watch?v=V5-0bJXTq4E)


