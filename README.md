# Scalable-Image-Storage-Website
Project update here:
https://github.com/yizhoushen/ECE1779-Project/tree/main/A2

## Introduction

We impleted an elastic web application with a memory cache consisting of a pool of storage nodes, where each node is an independent EC2 instance. The memory cache resize its pool of storage nodes on demand. We mainly consist of the following four components, each of which is implemented as a separate Flask instance.

* A manager-app that controls the size of the memcache pool. 
* An auto-scaler component that automatically resizes the memcache pool based on configuration values set by the manager-app. It monitors the miss rate of the mecache pool by getting this information using the AWS CloudWatch API. The auto-scaler is implemented as a stand-alone process that runs in the background. 
* The web front-end with the feature of routing requests to the memcache pool using a consistent hashing approach based on MD5 hashes. 
* The key-value memory cache.

We used following AWS technologies: EC2, RDS, S3, and CloudWatch. 

Note: The above content comes from Prof. Jacobsen at University of Toronto.

