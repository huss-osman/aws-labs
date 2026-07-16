<p align="center">
  <img width="500" style="margin-left: 40px;" alt="S3 Banner" src="https://github.com/user-attachments/assets/a18c8ba3-65ce-43b8-91e1-63c799c29444" />
</p>

# Amazon S3

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![Service](https://img.shields.io/badge/Service-S3-569A31)
![CDN](https://img.shields.io/badge/CDN-CloudFront-blue)
![DNS](https://img.shields.io/badge/DNS-Route%2053-purple)

Amazon Simple Storage Service (S3) is AWS's object storage service for securely storing, managing, and hosting static content and objects.

Combined with CloudFront and Route 53, content can be delivered globally through edge locations using HTTPS, caching, and DNS routing for improved performance, availability, scalability, reliability, and low-latency content delivery across distributed cloud environments efficiently.

The focus of this section is understanding how object storage, content delivery, DNS, and cloud hosting work practically in AWS environments.

---

## Learning Objectives

By working through these demonstrations, I aim to:

- Understand Amazon S3
- Configure static website hosting
- Deploy CloudFront distributions
- Configure Route 53 DNS records
- Secure websites using HTTPS
- Build globally distributed web applications

---

## Project

### **[S3 Static Website + CloudFront + Route 53](./04-s3-cloudfront-route53/)**

Provisioned a static website using Amazon S3, CloudFront, Route 53, and ACM to deliver secure content over HTTPS.
Implemented global content delivery, DNS routing, SSL/TLS encryption, caching, and automated website deployment using AWS services.
Built through hands-on cloud hosting, CDN configuration, DNS management, and modern web infrastructure practices.

<br>

<p align="center">
  <img width="850" alt="S3 CloudFront Architecture" src="images/s3-cloudfront-architecture.png" />
</p>

<br>

<p align="center">
  <a href="./04-s3-cloudfront-route53/"><strong>➡️ View Project</strong></a>
</p>

---

## Resources

- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
- [Amazon CloudFront Documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/)
- [Amazon Route 53 Documentation](https://docs.aws.amazon.com/Route53/)
