# 🌐 Lab 01: Hosting Your First Static Website in Azure

**Author:** Hazekiah Kennedy-Wilson  
**Estimated Time:** 30 Minutes  
**Difficulty:** Beginner  

---

## 📌 Lab Overview

In this lab, you will deploy your **first public-facing website in Microsoft Azure** using **Azure Blob Storage Static Website Hosting**.

Instead of managing servers, you will use a **Platform as a Service (PaaS)** approach—where Azure handles the infrastructure and you focus on your content.

---

## 🎯 Objective

By completing this lab, you will:

- Deploy a static website using Azure Storage
- Understand **PaaS** and **serverless hosting**
- Upload and manage web content in Azure
- Access your site via a public URL

---

## 🧱 Architecture Diagram

```
+-------------+
| User |
| (Internet) |
+------+------+
|
v
+-----------------------------+
| Public Endpoint URL |
| *.web.core.windows.net |
+-------------+---------------+
|
v
+-----------------------------+
| Azure Storage Account |
| $web Container |
| index.html |
+-----------------------------+
```

---

## 📋 Prerequisites

- [ ] Active Azure Subscription (Free Tier is fine)
- [ ] Basic text editor (VS Code, Notepad, etc.)

---

## 🏷️ Lab Variables (Naming Convention)

Use consistent naming:

- **Resource Group:**
```
rg-lab01-[yourname]
```
Example: rg-lab01-hazekiah

- **Location:**
```
East US
```

- **Storage Account Name:**
```
staticweblab01[yourname]
```
Example: staticweblab01hazekiah

> ⚠️ Important Rules:
> - Must be globally unique
> - Lowercase only
> - No special characters

---

## 🚀 Step-by-Step Instructions

---

## Phase 1: Create the Resource Group

1. Go to Azure Portal: https://portal.azure.com  
2. Search Resource groups  
3. Click + Create  

### Basics Tab:
- Subscription: Select your subscription  
- Resource Group:
```
rg-lab01-[yourname]
```
- Region: East US  

Click: Review + create → Create  

---

## Phase 2: Create the Storage Account

1. Search Storage accounts  
2. Click + Create  

### Basics Tab:
- Resource Group: Select your RG  
- Storage account name:
```
staticweblab01[yourname]
```
- Region: East US  
- Performance: Standard  
- Redundancy: Locally-redundant storage (LRS)  

Click: Review + create → Create  

Deployment takes ~30 seconds  
Click Go to resource when complete  

---

## Phase 3: Enable Static Website Hosting

1. In your Storage Account, go to:
```
Data management → Static website
```

2. Set:
- Static website: Enabled  
- Index document name: index.html  
- Error document path: 404.html (optional)  

3. Click Save  

Copy the Primary endpoint URL  

---

## Phase 4: Create Your Website File

Open your text editor and paste:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Cloud Site</title>
    <style>
        body { font-family: sans-serif; text-align: center; margin-top: 50px; background-color: #f0f0f0; }
        h1 { color: #0078d4; }
    </style>
</head>
<body>
    <h1>Hello from the Cloud!</h1>
    <p>This site is hosted on Azure Blob Storage.</p>
    <p>Deployed by: [Your Name]</p>
</body>
</html>
```

Save as:

```
index.html
```

---

## Phase 5: Upload Content

Go back to Azure Portal  

Navigate to:
```
Data storage → Containers
```

Open:
```
$web
```

Upload your index.html file  

---

## Phase 6: Validation

Open your endpoint URL in a browser  

You should see:
Hello from the Cloud!  

---

## 🛠️ Troubleshooting

404 Error:
- Make sure file is named index.html  
- Ensure it is in the $web container  

Storage name taken:
- Add numbers to make it unique  

---

## 🧹 Clean Up Resources

Go to Resource Groups  
Select your resource group  
Delete it to avoid charges  
