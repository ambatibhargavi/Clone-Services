# Netflix Clone DevOps Project
🎬 Project Overview
This project is a Netflix Clone built using HTML and CSS, containerized, and deployed using various DevOps tools and best practices. The aim was to implement a full CI/CD pipeline with Kubernetes and Docker for deployment, Argo CD for automated deployments, Jenkins for CI/CD, and SonarQube for code quality analysis.

🛠️ Technologies Used
HTML & CSS: Frontend for the Netflix clone, focusing on a responsive and user-friendly interface.
Docker 🐳: Containerized the application to make it portable and easy to deploy.
Kubernetes ☸️: Deployed the application in a scalable and managed environment.
Argo CD 🌀: Enabled GitOps for continuous delivery, automating Kubernetes deployments.
Jenkins ☕: Automated the CI/CD pipeline, handling build, test, and deployment tasks.
SonarQube 🔍: Integrated for code analysis to ensure high-quality and bug-free code.


📁 Project Structure
    NetflixClone-Service
    
├── Dockerfile          
 ├── k8s/               
├── Jenkinsfile         
├── ArgoCD/            
├── src/              
├── README.md          
└── sonar-project.properties 


🚀 Getting Started
Prerequisites
Docker: Ensure Docker is installed and running.
Kubernetes: Minikube or any Kubernetes cluster.
Argo CD: Installed and configured in your Kubernetes cluster.
Jenkins: Installed locally or on a server, with access to the Kubernetes cluster.
SonarQube: Set up a SonarQube instance for code analysis.
1. Build and Run with Docker
# Clone the repository
https://github.com/ambatibhargavi/Clone-Services.git
cd NetflixClone-Services

# Build Docker image
docker build -t netflix-clone .

# Run the container locally
docker run -p 8080:80 netflix-clone
Visit http://localhost:8080 to view the application.

<img width="1429" alt="Screenshot 2024-11-04 at 21 09 48" src="https://github.com/user-attachments/assets/a469c5aa-09c2-4609-9e3f-f840896347e7">

2. Deploy to Kubernetes
 # Apply Kubernetes configurations
kubectl apply -f k8s/{deployment , service files }

<img width="594" alt="Screenshot 2024-11-05 at 18 58 56" src="https://github.com/user-attachments/assets/429a376a-e986-4fad-8ee2-8f535213cb66">

3. Setup Argo CD for Continuous Deployment
. Add this GitHub repository to Argo CD.
. Use the Argo CD configuration files in the ArgoCD/ folder.
. Argo CD will continuously monitor the repository and deploy changes automatically.

![Screenshot 2024-10-28 at 12 21 09](https://github.com/user-attachments/assets/3cca9688-6b3e-45b2-9f35-a659a00f3296)

4. Jenkins CI/CD Pipeline
. Configure Jenkins with the Jenkinsfile present in the repository.
. The pipeline will:
. Build the Docker image
. Run tests and analysis using SonarQube
. Push the image to a Docker registry
. Deploy to Kubernetes

<img width="1408" alt="Screenshot 2024-11-05 at 19 03 55" src="https://github.com/user-attachments/assets/a2b99550-86cb-440e-b8ad-428a49f26684">

5. SonarQube Code Analysis
. SonarQube is configured to analyze code quality for the project.
. The configuration is set in sonar-project.properties.
. SonarQube will help maintain code quality by identifying bugs and vulnerabilities.

![Screenshot 2024-11-01 at 21 59 35](https://github.com/user-attachments/assets/fe9557f9-bda2-4c5c-8d3d-84740117911f)
![Screenshot 2024-11-01 at 20 03 50](https://github.com/user-attachments/assets/5ee04f83-1d82-404c-83d0-01daf97c1c23)

📝 Key Takeaways
Argo CD 🌀: Automates Kubernetes deployments with GitOps, making deployments reliable and version-controlled.
SonarQube 🔍: Ensures code quality by identifying bugs and vulnerabilities, improving overall maintainability.
🎉 Conclusion
This project demonstrates a full DevOps pipeline using modern tools for containerization, orchestration, CI/CD, and code quality. It’s an end-to-end example of how to manage applications in a scalable and automated environment.

Feel free to reach out with any questions or suggestions!









