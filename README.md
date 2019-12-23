# load_microservice

This is a test to make a deployment from google cloud platform

to make the deploy follow the next steps:

1. Create a dockerfile 
2. Add your credentials "gcloud container clusters get-credentials test-kubernetes --zone us-central1-a --project ornate-entropy-262918" 
3. Build a dockerfile "docker build -t  gcr.io/[proyect]/[name]:[label]  $PWD"
4. Make a push by typing "gcloud docker -- push  gcr.io/[proyect]/[name]:[label]"
5. Run the docker with kubernetes with " kubectl run hello-app 
    --image=gcr.io/[proyect]/[name]:[label] 
    --port= port of the app "
6. Make an expose by using "kubectl expose deployment 
    [name] --type="LoadBalancer""
7. The external ip is where you app is "kubectl get service [name] --watch"

To make changes

1. Make the changes
2. Recompile build -t ...
3. Type the comand line "kubectl set image 
    deployment/[name]
    [name]=gcr.io/[proyect]/[name]:[new label] 
    && echo 'image updated'"
