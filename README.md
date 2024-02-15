# My GKE Website Project
This project demonstrates deploying a website using a Docker image, Google Cloud Artifact Registry, and Google Kubernetes Engine (GKE) on Google Cloud Platform (GCP).

#Technology Stack:
Programming language: JavaScript
Web server: Nginx
Docker
Google Cloud Artifact Registry
Google Kubernetes Engine (GKE)

#Description:
This project builds a Docker image containing your website code and Nginx configuration, pushes it to Artifact Registry, and deploys it to a GKE cluster.

#Setup and Installation:
Clone this repository: git clone https://github.com/GNiruthian/Europe-Travel-Website-html-css-js
Change to the project directory
Configure Google Cloud resources: 
Enable the APIs https://console.cloud.google.com/flows/enableapi?apiid=compute.googleapis.com,artifactregistry.googleapis.com,container.googleapis.com&_ga=2.132260878.1867639901.1707852101-1802561548.1707851525
Build the Docker image: docker build -t [YOUR_IMAGE_NAME] . (replace [YOUR_IMAGE_NAME] with your desired name)
You can confirm that the image was built by running: docker images
You can run the docker image to test it: docker run -d -p 8080:80 [YOUR_IMAGE_NAME] .

#Deployment:
Authorize docker: gcloud auth configure-docker
Tag the image for Artifact Registry: docker tag [YOUR_IMAGE NAME] [LOCATION]-docker.pkg.dv/[PROJECT_ID]/[IMAGE_NAME]
Push the image to Artifact Registry: docker push [LOCATION]-docker.pkg.dv/[PROJECT_ID]/[IMAGE_NAME]
Go to Artifact Registry click on the [IMAGE_NAME]
Click on the 3 verticals dots to the right of the package
Select deploy to GKE and follow the prompts, including selecting an existing cluster, or creating a new one.
Select to expose the deployment as a new service and deploy.

#Usage:
Once deployed, access your website at the external IP address of your GKE cluster and the exposed port (e.g., http://<EXTERNAL_IP>:80).

#Additional Notes:
Remember to replace placeholders like [YOUR_IMAGE_NAME] and [PROJECT_ID] with your actual values.
This is a basic example, and you may need to adapt it to your specific website and infrastructure.
