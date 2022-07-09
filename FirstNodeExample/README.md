#It is my Node js application
#create node file with app.js and add code
#Prepare docker image with list of commands ref Dockerfile

#Prepare docker image
command:
    docker build -t sivakondal/mykubernetes:dockerNodeImage .

Push docker image to the dicker hub
    docker push sivakondal/mykubernetes:dockerNodeImage


#Run the app in container
    docker run -p5000:5000 sivakondal/mykubernetes:dockerNodeImage

###Run the application in K8 
step#1:
    cretae the hello-app-deployment.yml
step#2:
    kubectl create -f hello-app-deployment.yml
Step#3:
    Check for pods created and running
    kubectl get pods

    when you ran with minukube it shows like following
    NAME                                    READY   STATUS    RESTARTS   AGE
    hello-app-deployment-5b54cd6455-vx29g   0/1     Creating   

step#4:
    to run container on minikube need to prepare teh image with following var set
    minikube docker-env

step#5:
    kubectl get pods
NAME                                    READY   STATUS    RESTARTS   AGE
hello-app-deployment-6bdf967ff7-5gl2k   1/1     Running   0          3m47s

step#6: kubectl port-forward hello-app-deployment-6bdf967ff7-5gl2k 5000:5000
Forwarding from 127.0.0.1:5000 -> 5000
Forwarding from [::1]:5000 -> 5000
Handling connection for 5000
Handling connection for 5000





