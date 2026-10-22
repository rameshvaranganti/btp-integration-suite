<!-- loioabbb36a792c34d17a2562333060971ce -->

# Access the Message Service

Learn how to access the Message Service.



## Context

The Message Service provides a *Service Manager* UI. To use the Service Manager, follow these steps.

> ### Note:  
> The commands and examples in this document use the placeholder *<your-namespace\>*. Replace this with the actual namespace you defined during the deployment. If you kept the default settings, your namespaces are `edge-icell`, `edge-icell-services`, `edge-icell-ela`, or `istio-gateways`.



## Procedure

1.  To display the *Service Manager* port, use `kubectl port-forward ssb-solace-0 8080 -n <your-namespace>`.

2.  To get the admin user password, use `kubectl get secret ssbsecrets-solace--template="{{index .data.admin_password | base64decode}}" -n <your-namespace>`.

3.  Open an Internet browser using `localhost:8080` enter username `admin` and the password you retrieved before .


