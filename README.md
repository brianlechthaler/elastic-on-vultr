# Elastic Stack on Vultr *(unofficial)*
This repository has everything you need to run the Elastic stack on VKE using ECK.

## Setup
1. Setup VKE
2. Download your config, and copy it to `~/.kube/config`
3. Deploy Elasticsearch: `kubectl create -f elasticsearch.yaml`
4. Deploy Kibana: `kubectl create -f kibana.yaml`
5. Wait for everything to be deployed successfully before moving forward. Check progress with `kubectl get pods -w`

To access Kibana, simply execute the following command and visit https://127.0.0.1:5601 : `kubectl port-forward svc/kibana-sample-kb-http 5601`

## Disclaimer
This is not an official Vultr repository nor is it affiliated with them in any other way.

I am (at time of writing) an employee of Vultr, but this is a personal project.
