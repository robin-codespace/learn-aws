# Containerization
Containerization is a software deployment method that packages an application 
and all its dependencies into a single unit. This ensures the application 
runs consistently across any environment.

Key benefits:
- Consistent runtime environment
- Rapid deployment
- Resource efficiency
- Isolation
- Scalability

## Amazon Elastic Container Service (ECS)
[Official Documentation](https://aws.amazon.com/ecs/)

Amazon ECS is a fully managed container orchestration service that helps you easily 
deploy, manage, and scale containerized applications.

### Cluster
An ECS cluster is a logical grouping of EC2 instances or Fargate (serveless) tasks. 
Each cluster can run multiple services and tasks.

Key features:
- Supports EC2 and Fargate launch types
- Auto-scaling capabilities
- Multi-AZ support

### Service
ECS services allow you to run and maintain a specified number of task instances in 
your cluster. If any tasks fail or stop, the service scheduler launches another 
instance.

Key capabilities:
- Load balancer integration
- Auto-scaling
- Deployment strategies
- Service discovery integration

### Task
A task is an instance of a containerized application running in your cluster.

### Task Definition
Task definition is the blueprint for your containerized application, specifying:
- Container images
- CPU and memory requirements
- Networking mode
- Storage configurations
- IAM roles
- Logging configuration

### Launch Types
ECS supports two launch types that determine the infrastructure on which your tasks 
run:
- **EC2 Launch Type**: Tasks run on EC2 instances that you manage
- **Fargate Launch Type**: Serverless option where AWS manages the infrastructure

### How to expose your service

In Amazon ECS, there are several methods to expose your services for external access. 
Here I will cover the most common two.

#### 1. Load Balancer
Using a load balancer is the most common method for exposing ECS services:
- **Application Load Balancer (ALB)**: For HTTP/HTTPS traffic, supports path-based 
and host-based routing
- **Network Load Balancer (NLB)**: For TCP/UDP traffic, offers ultra-high performance 
and low latency


#### 2. API Gateway with Cloud Map
This combination is indeed a valid approach for exposing services, particularly 
well-suited for microservices architectures:
- **API Gateway**: Creates, publishes, and manages APIs with authentication, 
throttling, and other features
- **AWS Cloud Map**: Service discovery solution allowing applications to locate 
services by name



## Often Pair With
### Amazon ECR (Elastic Container Registry)
[Official Documentation](https://aws.amazon.com/ecr/)

Amazon ECR is a fully managed Docker container registry that makes it easy for 
developers to store, manage, and deploy Docker container images.

Key features:
- Deep integration with ECS
- Secure private repositories
- Lifecycle policies
- Image scanning
- Cross-region replication


## Helpful Documentation and Resources

### Official Blogs and Guides
- [AWS Architecture Blog: Serverless Container-based APIs with Amazon ECS and API 
Gateway](https://aws.amazon.com/blogs/architecture/field-notes-serverless-container-based-apis-with-amazon-ecs-and-amazon-api-gateway/)

### Tutorials and Best Practices
- [ECS Workshop](https://ecsworkshop.com/) - Interactive learning resource

### Community Resources
- [AWS Containers Blog](https://aws.amazon.com/blogs/containers/)
- [ECS FAQ](https://aws.amazon.com/ecs/faqs/)