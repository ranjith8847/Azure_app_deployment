# 🚀 Azure DevOps CI/CD Deployment — Node.js App on Azure App Service

This repository contains **end-to-end documentation** for deploying a **Node.js application** to **Azure App Service** using **Azure DevOps**, **Self-Hosted Agents**, **PostgreSQL Flexible Server**, and **Azure Front Door**.

It is structured as multiple markdown files under `docs/`, with images stored under `Images/`.

This README gives a clean, high-level overview of the entire deployment workflow.

---

# 📌 Overview

This project demonstrates a **production-grade cloud deployment workflow** using:

- Azure App Service (Application Hosting)  
- Azure PostgreSQL Flexible Server (Database)  
- Azure Front Door (Global Routing)  
- Azure VM (Self-Hosted DevOps Agent)  
- Azure DevOps Pipelines (CI/CD)  
- Resource Group (Resource Organization)

Each component is fully documented with screenshots and step-by-step instructions.

---

# 🧱 Architecture Components

This deployment uses the following Azure resources:

| Component                | Purpose                                         |
|--------------------------|-------------------------------------------------|
| **Resource Group**       | Logical grouping for all Azure resources        |
| **PostgreSQL Flexible Server** | Application database with HA/DR capabilities |
| **Virtual Machine (VM)** | Acts as the self-hosted agent for Azure DevOps  |
| **App Service**          | Hosts the Node.js application                   |
| **Azure Front Door**     | Global load balancing + routing                 |
| **Azure DevOps Pipelines** | CI/CD pipeline for automated build & release |

---

# 📂 Repository Structure

```
/
|-- docs/
| |-- ResourceGroup.md
| |-- Flexible_Server.md
| |-- AppService.md
| |-- FrontDoor.md
| |-- SelfHostedAgent.md
| |-- BuildPipelines.md
| |-- ReleasePipelines.md
|
|-- Images/
| └── All screenshots used in documentation
|
|-- README.md ← (You are here)
```


---

# 🏗️ Deployment Steps Summary

Below is a structured summary of everything documented inside `/docs`.

---

## 1️⃣ Resource Group

- Create a new Resource Group  
- Recommended region: **East Asia**  
- Choose a meaningful and identifiable name  

---

## 2️⃣ PostgreSQL Flexible Server

You learn:

- Why PostgreSQL Flexible Server is preferred  
- High Availability & Disaster Recovery  
- Creating a server **without firewall rules**  
- Connecting through **DBeaver**

Example screenshots:

![Enter image alt description](Images/tJJ_Image_1.png)
![Enter image alt description](Images/Iqd_Image_2.png)

---

## 3️⃣ App Service (Node.js App Hosting)

Includes:

- Creating an App Service  
- Not attaching a DB yet  
- Skipping repo connection for learning/demo  
- Screenshot walkthrough of the service creation  

Example:

![Enter image alt description](Images/jtG_Image_11.png)

---

## 4️⃣ Azure Front Door (Global Routing)

You configure:

- Frontend + Domain  
- Backend Pools  
- Adding both primary & secondary App Services  
- Creating Routing Rules  

Screenshots:

![Enter image alt description](Images/jnk_Image_16.png)
![Enter image alt description](Images/FZ2_Image_17.png)

---

## 5️⃣ Self-Hosted Agent (Azure VM)

You learn how to:

- Create a Linux VM  
- SSH into the VM  
- Download and configure the DevOps Agent  
- Generate Personal Access Tokens (PAT)  
- Install the service to run pipelines  

Example:

![Enter image alt description](Images/cfv_Image_22.png)

---

## 6️⃣ Build Pipelines (CI)

Includes:

- Classic Editor Pipeline  
- Using Command Line task  
- Publishing build artifacts  
- Assigning the self-hosted agent pool  
- Running the pipeline  

Example:

![Enter image alt description](Images/TCU_Image_38.png)

---

## 7️⃣ Release Pipelines (CD)

You learn:

- Creating a release pipeline  
- Adding the Build Artifact  
- Adding Azure App Service Deploy  
- Selecting subscription & authorizing  
- Deploying final application to App Service  

Example:

![Enter image alt description](Images/FIt_Image_45.png)

---

# 🏆 What You Learn From This Repo

✔ Azure Cloud Basics  
✔ Azure DevOps CI/CD Pipelines (Classic Editor)  
✔ VM Configuration & SSH  
✔ Setting Up Self-Hosted Agents  
✔ Deploying Node.js Apps on Azure App Service  
✔ PostgreSQL Integration  
✔ Global Traffic Routing with Azure Front Door  
✔ Real-world Enterprise Deployment Flow  

This documentation mimics **production workflows**, making it ideal for:

- Interviews  
- Portfolio projects  
- Cloud/DevOps learning  
- Deployment practice  

---

# 📘 How to Use This Repository

1. Navigate to the `docs/` directory  
2. Follow the steps in order:  
   - `ResourceGroup.md`  
   - `Flexible_Server.md`  
   - `AppService.md`  
   - `FrontDoor.md`  
   - `SelfHostedAgent.md`  
   - `BuildPipelines.md`  
   - `ReleasePipelines.md`  
3. Use the screenshots from `Images/` for full clarity  
4. Deploy your own end-to-end Azure pipeline  

---

# 🤝 Contributions

PRs and improvements are welcome.  
If you'd like to improve formatting, add automation scripts, or upgrade the pipeline YAML—feel free!

---

# ⭐ If you found this useful, star the repository!
