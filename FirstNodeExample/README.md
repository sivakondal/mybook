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

