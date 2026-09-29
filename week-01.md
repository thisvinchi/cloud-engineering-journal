# Week 01: Introduction to Cloud Computing

**Dates:** 07 Sep 2026 to 13 Sep 2026

## Summary
This week was Month 1, Week 1 of my cloud engineering course. It introduced what cloud computing is, why it replaced 
traditional infrastructure for most companies, and how cloud engineering fits into the software development lifecycle. I also 
learned the service models (IaaS, PaaS, SaaS), the deployment models (public, private, hybrid, multicloud), the shared 
responsibility model, and the tools and roles that make up the field. On the practical side, I set up my study environment 
and this Git repository to document my progress.

## What I Learned
###- What the cloud is
The cloud is a global network of remote servers housed in large data centers. Instead of storing data or running programs on 
my own hard drive, I access them over the internet. Providers such as AWS, Microsoft Azure, Google Cloud Platform, 
DigitalOcean, Huawei, Alibaba and Oracle Cloud own and run these data centers.

###- Cloud computing
It is the on demand delivery of computing resources (servers, storage, databases, networking, software, analytics and 
intelligence) over the internet. The benefits are faster innovation, flexible resources and economies of scale.

###- Cloud engineering
It is the work of designing, building and managing systems and services in the cloud so that they are scalable and flexible.

###- Traditional infrastructure vs cloud infrastructure 
Traditional infrastructure means buying and housing physical servers, paying upfront, and sizing for peak load, so much of it 
sits idle. Cloud infrastructure is rented from a provider, paid for only as used, and scaled in minutes. This is why most 
startups can now build and scale globally without millions in hardware costs.

###- Cloud service models
**- IaaS:** virtual servers and infrastructure (AWS EC2)
**- PaaS:** a platform for building and hosting apps (Google App Engine)
**- SaaS:** finished software over the internet (Google Workspace)
    The provider manages more and I manage less as I go from IaaS to PaaS to SaaS.

###- Cloud deployment models
Public cloud is run by a third party (AWS, Azure, GCP). Private cloud is dedicated to one organization, with more control but 
higher cost. Hybrid cloud combines public and private. Multicloud uses more than one provider, which avoids depending on a 
single vendor but adds complexity.

###- Shared responsibility model
The provider secures the cloud itself (data centers, hardware, core network). The customer secures what they put in it (data, 
access, configuration). In IaaS, I patch the operating system myself.

###- Cloud engineering and the SDLC
Cloud engineering supports every stage of the SDLC, from planning to maintenance. It turns "build, deploy, hope it works" 
into "build, test at scale, deploy automatically, monitor, improve continuously." Cloud engineers design, build, secure, 
monitor and optimize cloud systems.

###- Roles and tools
Roles include cloud architect, DevOps engineer, security engineer, network engineer and data engineer. The main tool areas 
are Infrastructure as Code (Terraform), CI/CD (GitHub Actions, Jenkins), monitoring (Prometheus, Grafana), containers 
(Docker, Kubernetes), networking and security, and AI and machine learning.

## What I Did (Hands On)
**Study environment**
- Installed VirtualBox and VS Code on my laptop
- Created an Ubuntu virtual machine in VirtualBox named altschool-server (2GB RAM, 2 CPUs, 20GB disk)
- Set up Vagrant with the ubuntu/focal64 box

```bash
# vagrant up
# vagrant ssh
```

## Resources Used
- Before the Cloud (Medium)
- AWS Shared Responsibility Model
- Unpacking the Shared Responsibility Model for Cloud Security (Medium)
- Altschool course videos
