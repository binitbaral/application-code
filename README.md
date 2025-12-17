*** This project demonstrates a fully automated CI/CD pipeline using GitHub, Google Cloud Build, Artifact Registry, and Cloud Run. ***

Whenever a developer pushes code to the GitHub repository:

    -Cloud Build is automatically triggered
    -A Docker container image is built
    -The image is pushed to Google Artifact Registry
    -Cloud Run fetches the latest image
    -The application is deployed as a new revision on Cloud Run


## Build docker container
docker build -t gcr.io/hopeful-list-446012-q4/weather-container:vo1 .

## test container locally
docker run -p 8080:8080 efb185ea5f87

## puch artiface to registry
docker push gcr.io/hopeful-list-446012-q4/weather-container:vo1
 
## deploy on cloud run
create a cloud run service,Deploy from the artiact registry, cloud run automatically creates a new version

## CI/CD using cloud build
-connect the github repo to cloud build
-create a build trugger
-configure trigger on the main branch