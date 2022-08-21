# Heimdal

https://heimdall.site

## Description

Application Dashboard Software

## Source

https://github.com/linuxserver/Heimdall

## Install with Argo CD

Use a central repository which links to all Apps which has to be deployed,
and add the App desciption there, or deploy the App for heimdal manually.
Find a sample in my [App of Apps Repo](https://github.com/wep4you/k8s-apps.git),
there is also sample definition for the [Heimdal App](https://github.com/wep4you/k8s-apps/blob/main/local/heimdal.yml)

## Install manual with kubectl

To add your own configuration, copy ```overlays/local``` to a new folder and change the files to your needs.
It's standard Kustomize format, in the example Ingress is patched with a new Domainname and the Deployment
is patched with another Version of the Image, instead of latest from the base file.

    ```
    kubectl apply -k overlays/local
    ```
