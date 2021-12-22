# Elastic Stack on Vultr *(unofficial)*
This repository has everything you need to run the Elastic stack on VKE using ECK.

## Setup
0. [Setup VKE](https://www.vultr.com/docs/vultr-kubernetes-engine/#How_to_Deploy_a_VKE_Cluster)
1. [Setup ECK](https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-deploy-eck.html)
2. Download your config, and copy it to `~/.kube/config`
3. Deploy Elasticsearch: `kubectl create -f elasticsearch.yaml`
4. Deploy Kibana: `kubectl create -f kibana.yaml`
5. Wait for everything to be deployed successfully before moving forward. Check progress with `kubectl get pods -w`
6. Modify the load balancer configurations as needed then deploy them if desired. This is completely optional.

To access Kibana, simply execute the following command and visit https://127.0.0.1:5601 : `kubectl port-forward svc/kibana-kb-http 5601`

You can find the password for the `elastic` user using this command:
`kubectl get secret elasticsearch-es-elastic-user -o=jsonpath='{.data.elastic}' | base64 --decode; echo`

## Disclaimer
This is not an official Vultr repository nor is it affiliated with them in any other way.

I am (at time of writing) an employee of Vultr, but this is a personal project.
