# Hosting a Static Portfolio

# **Project Title:**

# **Deploying and Securing a Static Portfolio Website Using Amazon S3, CloudFront, Route 53, and SSL Certificate Integration**

## **Project Overview**

### 

This project demonstrates how I designed, customized, and deployed my portfolio website using AWS services for **scalability**, **security**, and **high availability**.

Starting from editing a template in Visual Studio Code (VS Code) to registering a custom domain, configuring AWS S3 for static website hosting, and finally optimizing content delivery via CloudFront with SSL encryption, this workflow follows **cloud deployment best practices** suitable for professional-grade websites.

Additionally, this project will be **enhanced in future updates** to include automated **Continuous Integration and Continuous Deployment (CI/CD)** using **GitHub Actions** for fully automated code pushes to AWS.

## **Aims and Objectives**

- **Host a static website** on AWS for my portfolio.
- **Secure the website** with HTTPS using AWS Certificate Manager.
- **Integrate a custom domain** purchased from GoDaddy with AWS Route 53.
- **Improve performance** with CloudFront (Content Delivery Network).
- **Demonstrate end-to-end cloud deployment** from local editing to live production.

**Future-proof the workflow**

by planning CI/CD integration with GitHub Actions

## **Tools and Services Used**

- **VS Code** (Website editing & Live Server preview)
- **GoDaddy** (Domain purchase)
- **AWS S3** (Static website hosting)
- **AWS Route 53** (DNS & Hosted Zones)
- **AWS Certificate Manager (ACM)** (SSL/TLS Certificates)
- **AWS CloudFront** (Content Delivery Network)
- **Live Server Extension** (Real-time website preview)
- **GitHub** (Version control repository for future updates)
- **GitHub Actions** (Future automation for CI/CD)
- **Web Browser** (Testing and verification)

## **Steps Taken**

**1️⃣ Website Editing and Preview**

- **Action:**
    - Obtained a portfolio website template.
    - Customized it using **Visual Studio Code** to reflect my profile, skills, and projects.
    - Used **Live Server extension** to preview edits in real time.
- **Screenshot Placeholder:***[Insert screenshot of VS Code with website project open]*

![image.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/image.png)

- **Best Practice Note:** Editing locally before deployment ensures all files are optimized and errors fixed before going live.

**2️⃣ Domain Registration**

- **Action:**
    - Purchased the domain **hijoxcloud.online** from **GoDaddy**.
- **Screenshot Placeholder:***[Insert screenshot of GoDaddy domain dashboard]*

![image.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/image%201.png)

- **Best Practice Note:** Having a custom domain improves branding, professionalism, and SEO ranking.

**3️⃣ Creating an S3 Bucket for Static Hosting**

- **Action:**
    - In AWS, created a new **S3 bucket** named hijoxcloud.online.
    - Uploaded all website files (HTML, CSS, JS, images) from my local folder into the bucket.
- **Screenshot Placeholder:***[Insert screenshot of S3 bucket created and contents]*

![s3.1.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.1.png)

![s3.2.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.2.png)

- **Best Practice Note:** Using S3 for static websites is cost-effective, scalable, and serverless; perfect for low-maintenance deployments.

**4️⃣ Configuring Bucket Policy for Public Access**

- **Action:**
    - Opened **Permissions** tab in S3.
    - Edited the bucket policy to allow public GetObject access.
- **Screenshot Placeholder:***[Insert screenshot of bucket policy editor in AWS console]*

![s3.4.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.4.png)

- **Best Practice Note:** Only allow public access where necessary and use specific policies to limit exposure.

**5️⃣ Enabling Static Website Hosting**

- **Action:**
    - In the **Properties** tab, enable **Static Website Hosting**.
    - Set the **index document** to index.html.
- **Screenshot Placeholder:***[Insert screenshot of static hosting settings]*

![s3.3.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.3.png)

- **Best Practice Note:** This allows S3 to serve files directly over HTTP. However, S3 does not support HTTPS by default, hence the need for CloudFront later.

**6️⃣ Testing the S3 Website**

- **Action:**
    - Copied the **S3 Website Endpoint** into a browser and confirmed the site loads.
- **Screenshot Placeholder:***[Insert screenshot of browser showing live S3 site]*

![s3.6.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.6.png)

- **Best Practice Note:** At this stage, the site is functional but **not secured with HTTPS**.

**7️⃣ Creating a Hosted Zone in Route 53**

- **Action:**
    - Created a new hosted zone in AWS Route 53 for hijoxcloud.online.
    - Created an **A Record** with alias pointing to CloudFront (to be set up later).
- **Screenshot Placeholder:***[Insert screenshot of Route 53 hosted zone details]*

![s3.8.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.8.png)

- **Best Practice Note:** Using Route 53 ensures AWS-native DNS management and simplifies domain integrations.

**8️⃣ Linking GoDaddy with Route 53**

- **Action:**
    - Copied the **4 nameservers** from AWS Route 53.
    - In GoDaddy, changed **Nameservers** to **Custom** and pasted the AWS nameservers.
- **Screenshot Placeholder:***[Insert screenshot of GoDaddy nameserver change page]*

![s3.9.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.9.png)

- **Best Practice Note:** This step ensures that DNS resolution is managed by AWS, enabling full integration with other AWS services.

**9️⃣ Requesting an SSL Certificate via ACM**

- **Action:**
    - In **AWS Certificate Manager**, request a **public certificate** for hijoxcloud.online.
    - Validated ownership by creating a CNAME record in Route 53.
- **Screenshot Placeholder:***[Insert screenshot of ACM validation process]*

![s3.12.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.12.png)

- **Best Practice Note:** SSL certificates are essential for securing data, improving SEO, and building user trust.

**Creating a CloudFront Distribution**

- **Action:**
    - Created a **CloudFront distribution** with the S3 bucket as the origin.
    - Selected the custom SSL certificate.
    - Disabled unnecessary protection features for simplicity in this project (though enabling them is a best practice).
- **Screenshot Placeholder:***[Insert screenshot of CloudFront distribution settings]*

![s3.13.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.13.png)

![s3.14.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/s3.14.png)

- **Best Practice Note:** CloudFront acts as a CDN, caching your website globally for faster load times.

 **Final DNS Linking**

- **Action:**
    - Created an **A Record** in Route 53 with alias pointing to the CloudFront distribution.
    - Waited for propagation and tested https://hijoxcloud.online.
- **Screenshot Placeholder:***[Insert screenshot of final live website in browser with HTTPS lock icon]*

![image.png](Hosting%20a%20Static%20Portfolio%2024f5c4233bb680af9d1de8d10fded01d/image%202.png)

# **Planned Future Enhancement: CI/CD with GitHub Actions**

## **Future Plan:** This project will be upgraded to include **Continuous Integration and Continuous Deployment** using **GitHub Actions**.

- I will create a **GitHub repository** to store this website’s source code.
- A **GitHub Actions YAML pipeline** will be set up to automatically build, validate, and deploy the website to AWS S3.
- Any code changes pushed to the main branch will **automatically trigger deployment** to S3.
- CloudFront will be set to **invalidate cache** so changes are reflected instantly on the live site.
- **Best Practice Note:** This automation ensures faster development cycles, eliminates manual uploads, and keeps the live site always up-to-date.

## **Best Practices Demonstrated**

- Used **version-controlled local development** before deployment.
- Applied **least-privilege bucket policies**.
- Secured website with **SSL/TLS**.
- Integrated **CDN** for performance and reliability.
- Maintained a **custom domain** for branding.
- Designed with **future scalability and automation in mind**.

## **Lessons Learned**

- AWS S3 + CloudFront is a cost-effective and secure hosting solution for static websites.
- Domain-DNS integration between providers (GoDaddy + Route 53) requires careful configuration.
- SSL/TLS is not optional — it’s a must-have for modern websites.
- DNS propagation can take time; patience is key during final linking.
- The step-by-step workflow is reusable for future cloud deployments.

CI/CD pipelines will make deployment

**faster, more reliable, and hands-off**

© 2025 Iniabasi Okorie | All Rights Reserved

🔗 LinkedIn: [linkedin.com/in/iniabasiokorie](https://linkedin.com/in/iniabasiokorie)

📌 Please do not copy, reproduce, or republish this content without permission.

Created by Iniabasi Okorie

Not for unauthorized distribution

[linkedin.com/in/iniabasiokorie](http://linkedin.com/in/iniabasiokorie)