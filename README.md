# fastapi-meets-cloudrun

- pack build --builder gcr.io/buildpacks/builder:v1 gcr.io/[PROJECT-ID]/victor-gcr
- docker push gcr.io/[PROJECT-ID]/victor-gcr
- gcloud run deploy victor-gcr --image gcr.io/[PROJECT-ID]/victor-gcr --platform managed --region europe-west1 --no-allow-unauthenticated
- curl -H "Authorization: Bearer $(gcloud auth print-identity-token)" $SERVICE_URL
- While Cloud Run does not charge when the service is not in use, you might still be charged for storing the container image in Container Registry: https://cloud.google.com/container-registry/docs/managing#deleting_images 
