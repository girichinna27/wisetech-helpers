# wisetech-helpers

PRE_REQUISITES  
bash installed  
helm installed  
yq installed   (sudo wget https://github.com/mikefarah/yq/releases/latest/download/yq_linux_amd64 -O /usr/bin/yq && chmod +x /usr/bin/yq)

step 1. clone this repo

for each k8s repo repeat these steps
step 1. clone the k8s manifest repo and follow these two steps  
step 2.  cp the files in this folder runonceper-everynewapp to the base dir of the cloned repo
step 3. cd <base directory of the k8s manifest repo>

        and for every new app in the repo repeat these steps
  
       step 1. run the script --  ./transform.sh <folder containing all the micro-services> 
         this will create a legitimate helm chart for each microservice
       step 2. run the acript -- ./create-mainchart.sh <folder containing all the micro-services>  
       this script  will create a mainchart that combines each of the microservices to create a legitimate helm chart

decide whether to commit the scripts and templates copied from this repo to the k8s repo or not
git add  -A
git commit -m " created microservices helm charts and application helm charts"
git push 
