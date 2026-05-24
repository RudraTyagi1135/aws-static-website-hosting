# ☁️ AWS S3 Static Website Hosting with ACL & Bucket Policy

<p align="center">

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws)
![Amazon S3](https://img.shields.io/badge/Amazon-S3-red?style=for-the-badge&logo=amazons3)
![Static Hosting](https://img.shields.io/badge/Static-Website-blue?style=for-the-badge)
![Security](https://img.shields.io/badge/S3-Security-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

</p>

---

# 📌 Project Overview

This project demonstrates how to host a static website using **Amazon S3** while implementing secure access control using:

- S3 Bucket ACLs
- Bucket Policies
- Public Access Configuration

The project focuses on:
- cloud storage fundamentals
- static website deployment
- AWS access control mechanisms
- object-level permissions
- bucket-level security enforcement

A security rule was implemented to prevent accidental deletion of the website’s main entry file:

```text
index.html
```

---

# 🎯 Project Objective

The goal of this project was to understand how AWS S3 can be used not only as object storage, but also as a lightweight cloud hosting solution.

This project demonstrates:

```text
Static Website Files
        ↓
Amazon S3 Bucket
        ↓
ACL-Based Public Access
        ↓
Bucket Policy Security Rules
        ↓
Public Website Hosting
```

The implementation focuses on:
- practical AWS console operations
- static hosting workflows
- cloud security fundamentals
- troubleshooting real-world S3 hosting issues

---

# ✨ Core Features

## 🌐 Static Website Hosting

- Hosted website directly from Amazon S3
- Configured index document
- Enabled public website endpoint access

---

## 🔓 Public Access Management

- Enabled controlled public access
- Configured object-level ACL permissions
- Managed Block Public Access settings

---

## 🔐 Bucket Policy Security

Implemented a bucket policy that:

- prevents deletion of `index.html`
- protects the website entrypoint
- demonstrates explicit deny rules

---

## ⚡ Lightweight Cloud Deployment

Benefits:
- serverless hosting
- no backend infrastructure
- low operational complexity
- highly scalable static delivery

---

# 🧠 What This Project Demonstrates

This project demonstrates practical understanding of:

- Amazon S3 workflows
- static website hosting
- ACL vs bucket policy behavior
- AWS storage security
- public object access configuration
- object-level permission management
- bucket-level policy enforcement
- troubleshooting S3 hosting issues

---

# 🏗️ System Architecture

```text
Static Website Files
            ↓
Amazon S3 Bucket
            ↓
Bucket ACL Configuration
            ↓
Bucket Policy Rules
            ↓
Static Website Hosting
            ↓
Public Website Endpoint
```

---

# ⚙️ Architecture Breakdown

---

# ☁️ Amazon S3 Layer

Responsibilities:
- object storage
- website hosting
- public file serving
- scalable static content delivery

---

# 🔓 ACL Layer

ACLs were used to:
- enable public-read access
- expose static website assets
- configure object-level visibility

Example:
- HTML
- CSS
- JS
- image assets

---

# 🔐 Bucket Policy Layer

Bucket policy responsibilities:
- apply explicit deny rules
- enforce file protection
- prevent accidental deletion

Implemented protection target:

```text
index.html
```

---

# 📂 Repository Structure

```text
AWS_S3_STATIC_WEBSITE_HOSTING/
│
├── architecture/
│   ├── architecture.png
│   └── architecture.eraser
│
├── screenshots/
│   ├── create-bucket.png
│   ├── upload-files.png
│   ├── enable-hosting.png
│   └── webpage.png
│
├── policies/
│   └── s3policy.txt
│
├── website/
│   ├── index.html
│   └── assets/
│
├── README.md
└── LICENSE
```

---

# 🔄 Deployment Workflow

```text
Create S3 Bucket
        ↓
Disable Block Public Access
        ↓
Upload Website Files
        ↓
Enable Static Website Hosting
        ↓
Apply Public Read ACL
        ↓
Attach Bucket Policy
        ↓
Access Public Website Endpoint
```

---

# 🔐 Bucket Policy Example

The following policy prevents deletion of the website entry file:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PreventIndexDeletion",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:DeleteObject",
            "Resource": "arn:aws:s3:::static-website-host-p1/index.html"
        }
    ]
}
```

---

# 📸 Project Screenshots

---

## ☁️ S3 Bucket Creation

```markdown
![Create Bucket](screenshots/create-bucket.png)
```

---

## 📤 Uploading Website Files

```markdown
![Upload Files](screenshots/upload-files.png)
```

---

## 🌐 Enabling Static Website Hosting

```markdown
![Enable Hosting](screenshots/enable-hosting.png)
```

---

## 💻 Live Hosted Website

```markdown
![Webpage](screenshots/webpage.png)
```

---

# 🚀 How To Reproduce

---

# 1️⃣ Create S3 Bucket

Create an S3 bucket with:

```text
ACL Enabled → Bucket Owner Preferred
```

---

# 2️⃣ Disable Block Public Access

Inside bucket permissions:
- disable public access restrictions
- allow website object visibility

---

# 3️⃣ Upload Website Files

Upload:
- `index.html`
- CSS assets
- JS assets
- images

---

# 4️⃣ Enable Static Website Hosting

Inside:
```text
Bucket → Properties → Static Website Hosting
```

Configure:
- index document
- optional error document

---

# 5️⃣ Configure Public Access

Apply:
- public-read ACL
- object-level access permissions

---

# 6️⃣ Attach Bucket Policy

Attach the deny-delete policy for:

```text
index.html
```

---

# 📊 ACL vs Bucket Policy

| Feature | ACL | Bucket Policy |
|---|---|---|
| Scope | Object-level | Bucket-level |
| Public Read Access | ✅ | ✅ |
| Explicit Deny Rules | ❌ | ✅ |
| Fine-Grained Security | Limited | Strong |
| Recommended AWS Approach | Legacy / Simple | Preferred |

---

# 🎯 Why These AWS Services Were Chosen

---

# ☁️ Amazon S3

### Why S3?

Amazon S3 provides:
- highly durable storage
- global scalability
- low operational overhead
- serverless static hosting

### Compared To Traditional Hosting

Compared to:
- VPS hosting
- Apache/Nginx servers

S3 offers:
- no server maintenance
- simplified deployment
- lower infrastructure complexity

---

# 🔓 ACLs

### Why ACLs?

ACLs enable:
- object-level public visibility
- fast website asset exposure

Useful for:
- beginner AWS hosting workflows
- understanding legacy S3 permission models

---

# 🔐 Bucket Policies

### Why Bucket Policies?

Bucket policies allow:
- explicit deny rules
- centralized permission management
- stronger security enforcement

This project specifically uses policies to:
- protect `index.html`
- prevent destructive operations

---

# 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Amazon S3 | Static website hosting |
| S3 ACLs | Public object access |
| Bucket Policies | Security enforcement |
| AWS Console | Service configuration |
| HTML/CSS | Website frontend |

---

# 📊 Engineering Highlights

- Cloud-native static hosting
- S3 security configuration
- Public access troubleshooting
- ACL permission handling
- Bucket policy enforcement
- Lightweight serverless deployment
- Practical AWS console operations

---

# ⚠️ Common S3 Hosting Problems Solved

This project involved troubleshooting issues such as:

- Access Denied errors
- Block Public Access conflicts
- missing public-read ACLs
- incorrect bucket policy configuration
- missing index document configuration

---

# 🚧 Current Limitations

Current constraints include:

- HTTP-only hosting
- no CDN integration
- no HTTPS certificates
- no domain mapping
- no deployment automation
- no CI/CD integration

---

# 🚀 Planned Future Improvements

Future improvements include:

- Amazon CloudFront integration
- HTTPS support with ACM
- Route53 custom domain setup
- Infrastructure as Code using Terraform
- automated deployment pipelines
- GitHub Actions integration
- S3 versioning
- lifecycle management policies

---

# ☁️ Recommended Future Architecture

```text
Static Website Files
        ↓
Amazon S3
        ↓
CloudFront CDN
        ↓
AWS Certificate Manager
        ↓
Route53 Custom Domain
        ↓
Global Static Website Delivery
```

---

# 🎓 Learning Outcomes

This project helped build understanding of:

- AWS S3 hosting workflows
- ACL vs bucket policy differences
- object-level vs bucket-level security
- cloud storage permissions
- static website deployment
- troubleshooting cloud hosting systems

---

# 📌 Strategic Engineering Value

This project demonstrates foundational cloud engineering skills including:

- AWS storage systems
- static hosting deployment
- access control design
- bucket security policies
- cloud troubleshooting workflows

These are practical foundational skills for:
- cloud engineering
- DevOps
- MLOps infrastructure
- AWS operations roles

---

# 👨‍💻 Author

## Rudra Tyagi

### Focus Areas

- AWS ML Engineering
- Cloud Infrastructure
- MLOps
- AI Infrastructure
- Cloud-Native Systems

---

# ⭐ Recruiter Notes

This project demonstrates:
- hands-on AWS usage
- cloud storage configuration
- security policy understanding
- real-world hosting troubleshooting
- foundational cloud engineering workflows

---

# 📜 License

MIT License — see `LICENSE` file for details.

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
