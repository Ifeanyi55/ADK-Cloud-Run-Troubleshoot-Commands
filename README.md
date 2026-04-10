# ADK-Cloud-Run-Troubleshoot-Commands
Added commands for properly configuring Cloud Run on a new GCP Project.


### Set project ID globally
```gcloud config set project PROJECT_ID```

### Correct service account address in .env
```lab2-cr-service@PROJECT_ID.iam.gserviceaccount.com```

### Add .env back to session
```source .env```

### Grant storage object viewer role to the service account
```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
    --role="roles/storage.objectViewer"
```

### Grant artifact registry role to the service account
```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
    --role="roles/artifactregistry.writer"
```

### Grant logging permissions
```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
    --role="roles/logging.logWriter"
```

### Grant storage permissions
```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
    --role="roles/storage.objectAdmin"
```

### Grant artifact registry writer
```
gcloud projects add-iam-policy-binding PROJECT_ID \
    --member="serviceAccount:PROJECT_NUMBER-compute@developer.gserviceaccount.com" \
    --role="roles/artifactregistry.writer"
```
