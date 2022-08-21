# Heimdal

https://heimdall.site

## Description

Application Dashboard Software

## Source

https://github.com/linuxserver/Heimdall

## Option 1 - Installation manual with kubectl

To add your own configuration, copy ```overlays/local``` to a new folder and change th files to your needs.
Its standard Kustomize format, in the example Ingress is patched with a new Domainname and the Deployment
is patched with another Version of the Image, instead of latest from the base file.

    ```
    kubectl apply -k overlays/local
    ```
## Option 2 - Installation manual with Argo CD

The File ```app-local.yml``` is a Resource Definition for an Argo CD Application. Change the path within this file 
to the new folder you created, and add it with kubectl to your Custer where ArgoCD is running. 

    ```
    kubectl apply -f app-local.yml
    ```
## Option 3 - Installation automatically with Argo CD App of Apps
If you already have a main Application.yml, which just references other Repositories with Applications (App of Apps),
just add the repo of your newly created app-local.yml there, and Argo will start deploying automatically.
