# k8s-drupal-blueprint

## Google Kubernetes Engine

```
gcloud beta container --project "formation-222117" clusters create "standard-cluster-1" \
      --zone "us-central1-a" --no-enable-basic-auth --cluster-version "1.13.6-gke.13" \
      --machine-type "n1-standard-2" --image-type "COS" --disk-type "pd-standard" \
      --disk-size "100" --local-ssd-count "1" --node-labels env=staging \
      --metadata disable-legacy-endpoints=true --scopes  "https://www.googleapis.com/auth/devstorage.read_only","https://www.googleapis.com/auth/logging.write","https://www.googleapis.com/auth/monitoring","https://www.googleapis.com/auth/servicecontrol","https://www.googleapis.com/auth/service.management.readonly","https://www.googleapis.com/auth/trace.append" \
      --num-nodes "3" --enable-cloud-logging --enable-cloud-monitoring \
      --enable-ip-alias --network "projects/formation-222117/global/networks/default" \ 
      --subnetwork "projects/formation-222117/regions/us-central1/subnetworks/default" \
      --default-max-pods-per-node "110" --addons HorizontalPodAutoscaling,HttpLoadBalancing \ 
      --enable-autoupgrade --enable-autorepair
```
