You should handle this part by yourself. The following link provides very good tutorial if you are using digital ocean.
https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nginx-ingress-with-cert-manager-on-digitalocean-kubernetes
For other cloud providers it might be even easier to configure ingress controller.

The one liner to install ingress controller.
`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.5.1/deploy/static/provider/scw/deploy.yaml`
This will create ingress controller and create loadbalancer provided by your cloud provider. 
Be warned that LB costs you money.

After creating a ingress like this, then you will need to apply `ingress_nginx_svc.yaml` to tune your DO-LB. More information below:
https://github.com/digitalocean/digitalocean-cloud-controller-manager/blob/master/docs/controllers/services/annotations.md
