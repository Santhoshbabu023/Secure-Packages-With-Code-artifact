# 📦 Secure Packages with AWS CodeArtifact

## 🚀 Project Overview

This project demonstrates how to set up **AWS CodeArtifact** for securely managing software packages in a DevOps environment. I configured IAM roles, integrated CodeArtifact with a Maven-based Java web app, and successfully published custom packages to a private repository.

This is **Part 3** in my ongoing DevOps series focused on building a CI/CD pipeline.

---

## 🛠️ Key Tools & Concepts

- **AWS CodeArtifact** – for secure and scalable package management.
- **AWS CLI** – for authenticating and managing CodeArtifact interactions.
- **IAM Roles & Policies** – for secure and temporary access using EC2.
- **Maven** – for Java dependency management and project compilation.

---

## 📁 Project Goals

- Set up and configure AWS CodeArtifact.
- Grant secure access via IAM roles.
- Connect Maven to CodeArtifact using a settings.xml file.
- Test and verify secure dependency resolution.
- Publish and manage custom packages.

---

## 🔐 CodeArtifact Security

### Problem Encountered
I initially faced errors related to:
- Expired or missing AWS credentials.
- Incorrect IAM permissions.
- Wrong AWS region configuration.

### ✅ Solution
- Fixed typos in IAM policies.
- Attached the policy to an EC2 instance role.
- Verified region and authentication setup.

### IAM Policy Highlights
The attached IAM role allowed:
- Fetching CodeArtifact auth tokens.
- Reading packages.
- Accessing repository endpoints.

IAM roles are preferred for:
- Temporary credentials (no hardcoded secrets).
- Least-privilege access.
- Auto-rotated tokens.
- Secure service-to-service authentication.

---

## ⚙️ Maven Integration

- Used a custom `settings.xml` to point Maven to the private CodeArtifact repo.
- Configured Maven to authenticate using AWS CLI-generated tokens.
- Verified builds pulled dependencies from CodeArtifact first, then Maven Central if not found.

---

## ✅ Results & Verification

- Successfully compiled the Java web app using Maven.
- Verified that dependencies were fetched from CodeArtifact.
- Uploaded and published a custom package to the repository.
- Observed caching for faster and efficient builds.

---

## 📚 What I Learned

- Setting up and configuring AWS CodeArtifact for private Maven repositories.
- Managing secure access via IAM roles and temporary credentials.
- Verifying Maven builds with CodeArtifact integration.
- Publishing and managing internal packages securely.

---

## 🔮 Next Steps

In the **next project**, I will integrate **AWS CodeBuild** to automatically compile and build the web app, eliminating manual build commands and moving closer to a fully automated CI/CD pipeline.

Stay tuned!

---
