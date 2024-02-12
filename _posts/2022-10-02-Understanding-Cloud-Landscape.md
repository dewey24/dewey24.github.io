---
title: <br/><br/><br/>The Cloud Services Landscape<br/><br/><br/>
date: "02 10 2022"
show_date: true
layout: single
classes: wide
author_profile: true
header:
  overlay_image: /assets/images/aws_azure_gcp.jpeg
  #overlay_color: "#333"
  show_overlay_excerpt: false
  #teaser: /assets/images/experiments.jpeg
  caption: "Photo Credits: [**moveworkforward.com**](https://www.moveworkforward.com/blog/aws-vs-azure-vs-google-cloud-which-cloud-services-is-better-for-enterprises)" 
tags:
- Product
- Analytics
- Cloud
toc: true
---

## Key DevOps Tools & Cloud Services


|    | **DevOps Tool / Cloud Service**         | **Open Source**                     | **AWS**                   | **Azure**                 | **GCP**                   |
|----|---------------------------|-------------------------------|----------------------------|----------------------------|----------------------------|
| 1. | **Version Control Systems**  | * Git            | * AWS CodeCommit                 | * Azure Repos <br/> * GitHub Enterprise                 | * GCP Cloud Source Repositories              |
| 2. | **Build Tools**  | * Apache Maven <br/> * Gradle <br/> * SBT  <br/> * Poetry          | * AWS CodeBuild                 | * Azure DevOps                | * GCP Cloud Build                |
| 3. | **CI/CD**  | * Jenkins            | * AWS CodeDeploy <br/> * AWS CodePipeline                  | * Azure DevOps               | * GCP Cloud Deploy                |
| 4. | **Container Orchestration** | * Docker Swarm <br/> * Kubernetes            | * AWS Elastic Kubernetes Service (EKS)                 | * Azure Kubernetes Service (AKS)                | * Google Kubernetes Engine (GKE)                |
| 5. | **Configuration Management Tools** | * Puppet <br/> * Chef <br/> * Ansible            | * AWS Config                 | * Azure Policy               | * GCP Asset Inventory                |
| 6. | **Continuous Monitoring Tools** | * Grafana <br/> * ELK <br/> * Nagios            | * AWS CloudWatch                 | * Azure Monitor                | * GCP Cloud Monitoring                |
| 7. | **Workflow Orchestration** | * Apache Airflow <br/> * Oozie            | * AWS Step Functions                 | * Azure Logic Apps                | * Workflows                |
| 8. | * **Storage** <br/> * **Infrequently accessed storage** | * Hadoop File System (HDFS) <br/> * Ceph            | * AWS Simple Storage Service (S3) <br/> * Amazon S3 Glacier                 | * Azure Blob Storage <br/> * Azure Archive Storage               | * Cloud Storage <br/> * Cloud Storage Archive|
| 9. | **Compute** |             | * Amazon Elastic Compute Cloud (EC2)                 | * Azure Virtual Machines                | * GCP Compute Engine                |
| 10. | **Data Warehouse** | * Spark SQL <br/> * Apache Hive <br/> * Presto            | * Amazon Redshift <br/> * Amazon Athena                 | * Azure Synapse Analytics                | * BigQuery                |
| 11. | **Serverless** <br/> **(functions as a service)** | * Knative <br/> * OpenFaaS <br/> * Fn           | * AWS Lambda                  | * Azure Functions Serverless Compute               | * Cloud Functions                 |
| 12. | **ML/AI Training Compute** |             | * AWS Elastic Compute Cloud (EC2) <br/> * AWS UltraClusters                 | * Azure Virtual Machines <br/> * GPU Optimized VMs                | * Cloud GPUs <br/> * Cloud TPU                |
| 13. | **Container Registry** | * Docker Registry <br/> * Quay            | * Amazon Elastic Container Registry (ECR)                 | * Azure Container Registry                | * Artifact Registry                |
| 14. | **Job Scheduling** | * Apache ActiveMQ            | * Amazon EventBridge                 | * Azure Scheduler                | * Cloud Scheduler                |
| 15. | **Event Handling** | * Apache Kafka <br/> * Trigger Mesh            | * AWS EventBridge                 | * Azure Event Grid                | * Eventarc                |
| 16. | **Service Mesh**             | * OpenStack <br/> * OpenVPN            | * Amazon VPC                 | * Azure VPN Gateway                | * Cloud Router                |
| 17. | **Identity & Access Management** | * Open Identity Platform <br/> * Apache Syncope <br/> * Keycloak            | * Amazon Identity and Access Management                 | * Azure Identity Management                | * Identity and Access Management                |
| 18. | **Logging** | * Grafana Loki <br/> * OpenObserve            | * Amazon CloudWatch Logs                 | * Azure Monitor Logs                | * Cloud Logging                |
| 19. | **Data Streaming** | * Apache Kafka            | * AWS Kinesis                 | * Azure Service Bus Messaging               | * Pub/Sub               |
| 20. | **Audit Logging** |  * Graylog           | * AWS CloudTrail                 | * Azure Audit Logs                | * Cloud Audit Logs                |
| 21. | **In-Memory Cache** | * Memcached <br/> * Redis            | * AWS ElastiCache                 | * Azure Cache               | * GCP Memorystore                |
| 22. | **Data Processing** | * Apache Spark            | * AWS Elastic MapReduce (EMR)                 | * Azure Data Lake Analytics               | * GCP Dataproc                |
| 23. | **Document Database** | * MongoDB            | * Azure Cosmos DB                 | * Amazon DocumentDB <br/> * Amazon DynamoDB               | * Firestore               |
| 24. | **Persistent Disk** | * OpenEBS <br/> * Portworx            | * Amazon Elastic Block Store (EBS)                | * Azure Disk Storage               | * Block storage                |
| 25. | **Serverless Data Integration** | * Airbyte <br/> * Talend <br/> * Airflow           | * AWS Glue                | * Azure Data Factory              | * GCP Dataflow               |
| 26. | **Load balancing** | * Traefik <br/> * OpenStack           | * AWS Elastic Load Balancing                | * Azure Load Balancer              | * Cloud Load Balancing              |
| 27. | **NoSQL Database** | * Apache Cassandra            | * Amazon DynamoDB                 | * Azure Cosmos DB                | * Cloud Bigtable                |
| 28. | **Machine Learning** | * H2O.ai <br/> * MLflow <br/> * Cortex <br/> * Ploomber <br/> * Zilliz's Towhee             | * Amazon Sagemaker                | * Azure AI Platform <br/> * Azure Machine Learning                | * Vertex AI                 |
| 29. | **Graph DBMS** | * Neo4j            | * AWS Neptune               | * Azure Cosmos DB              |               |
| 30. | * **Command-line interface (CLI)** <br/> * **Client libraries** |             | * AWS SDKs <br/> * AWS CLI                | * Azure SDKs <br/> * Azure CLI               | * Cloud SDK                |



* [Cloud Services : AWS vs Azure vs GCP](https://cloud.google.com/docs/get-started/aws-azure-gcp-service-comparison)
* [AWS to Azure services comparison](https://learn.microsoft.com/en-us/azure/architecture/aws-professional/services)
