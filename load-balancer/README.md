<p align="center">
  <img width="500" style="margin-left: 40px;" alt="Application Load Balancer Banner" src="https://github.com/user-attachments/assets/f51f18e0-55aa-487f-aa51-e6ab1d94deaa" /> 
</p>

# Application Load Balancer

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![Service](https://img.shields.io/badge/Service-Application%20Load%20Balancer-orange)
![Availability](https://img.shields.io/badge/Focus-High%20Availability-blue)
![Traffic](https://img.shields.io/badge/Traffic-Load%20Balancing-green)

Application Load Balancer (ALB) is AWS's Layer 7 load balancing service that distributes HTTP and HTTPS traffic across multiple targets.

Traffic is routed using listeners, target groups, health checks, and routing rules. This enables highly available, scalable, and fault-tolerant applications while efficiently distributing client requests across multiple resources and services within AWS at scale in production reliably.

The focus of this section is understanding how load balancing, traffic distribution, high availability, and scalability work practically.

---

## Learning Objectives

By working through these demonstrations, I aim to:

- Understand Application Load Balancers
- Configure listeners and target groups
- Perform health checks
- Distribute traffic across EC2 instances
- Build highly available architectures
- Deploy scalable AWS applications

---

## Project

### **[Application Load Balancer](./03-application-load-balancer)**

Provisioned an Application Load Balancer with multiple Amazon EC2 instances distributed across Availability Zones using AWS networking services.
Implemented load balancing, target groups, health checks, Security Groups, and scalable traffic distribution across web servers.
Built through hands-on cloud networking, high-availability architecture, infrastructure deployment, and AWS load balancing practices.

<br>

<p align="center">
  <img width="850" alt="Application Load Balancer Architecture" src="https://github.com/user-attachments/assets/025ca542-343f-45ed-8b71-e1146bdfeb90" /> 
</p>

<br>

<p align="center">
  <a href="./03-application-load-balancer/"><strong>➡️ View Project</strong></a>
</p>

---

## Resources

- [Elastic Load Balancing Documentation](https://docs.aws.amazon.com/elasticloadbalancing/)
- [Application Load Balancers User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/)
- [Target Groups Documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)
