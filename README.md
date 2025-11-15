This project contains my personal portfolio — a simple, fast, and fully responsive static website built using **HTML**, **CSS**, and **JavaScript**.

Visit the live site here:  
**https://suganpreetham.github.io/Dockerized_CICD_Pipeline/**

🛠️ What This Project Contains
- `index.html` – Main structure of the portfolio  
- `style.css` – Styling and layout  
- `script.js` – Basic interactivity  
- `Dockerfile` – (Optional) Used for containerizing the site  
- `Jenkinsfile` – For CI/CD pipeline (if used in a DevOps demo setup)

This portfolio can be deployed in two ways:

### 1️⃣ Automated Deployment (CI/CD on AWS EC2)
I built a full CI/CD pipeline using **Jenkins + Docker + GitHub Webhooks** that:
- Pulls the code automatically on each push  
- Builds a Docker image  
- Deploys the container on an EC2 instance  
- Runs health checks and supports rollback  

2️⃣ Permanent Public Hosting (GitHub Pages)
Since EC2 cannot stay online for free forever, the live version of the portfolio is hosted using **GitHub Pages**, which provides:
- 24/7 free hosting  
- CDN-backed fast loading  
- Zero maintenance  

Live site:  
**https://suganpreetham.github.io/Dockerized_CICD_Pipeline/**
