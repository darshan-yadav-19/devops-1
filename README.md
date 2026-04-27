\# DevOps CI/CD Pipeline Project



\*\*Built by:\*\* Darshan Yadav



\## What This Project Does



Every time code is pushed to this GitHub repo, a Jenkins pipeline automatically builds a Docker image and deploys it to an AWS EC2 server. The webpage is live at http://3.108.60.157



\## Tech Stack



| Tool | Purpose |

|---|---|

| Git + GitHub | Version control and source of truth |

| Terraform | Provisioned AWS EC2 infrastructure as code |

| AWS EC2 | Cloud server (t2.micro, ap-south-1, Ubuntu 24.04) |

| Docker | Containerized the web application |

| Jenkins | CI/CD automation engine |

| GitHub Webhook | Triggers Jenkins on every push |



\## Pipeline Stages



1\. \*\*Clone\*\* — Jenkins pulls latest code from GitHub

2\. \*\*Build\*\* — Docker builds image from Dockerfile

3\. \*\*Deploy\*\* — Old container removed, new container started on port 80



\## Project Structure

hello-devops/

├── index.html        ← The webpage

├── Dockerfile        ← Docker build instructions

├── Jenkinsfile       ← Pipeline stages

└── terraform/

├── main.tf       ← EC2 + security group + key pair

├── variables.tf  ← Region, AMI, instance type

└── outputs.tf    ← Public IP + SSH command



\## How To Trigger The Pipeline



Just push any code change:



```bash

git add .

git commit -m "your message"

git push origin main

```



Jenkins picks it up automatically via GitHub webhook and deploys within seconds.

