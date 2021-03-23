---
title: "Deployments without worry"
chapter: true
weight: 22
---

# Deployments with Kubernetes?
Kubernetes (k8s) is a container orchestration platform allowing organizations to scale their services and workloads quickly. If you are working with containers or microservices, k8s may be a great use case for you.  Kubenetes deployments are container image deployments which target k8s-based environments.  

Amazon has released a managed k8s service called Elastic Kubernetes Service (EKS).  Amazon EKS helps you provide highly-available and secure clusters and automates key tasks such as patching, node provisioning, and updates. While AWS provides the platform on which to run your containerize applications deploying them in a scalable, repeatable and reliable way is where Harness comes in.

# How does Harness help with EKS deployments?

Harness has first-class support for Kubernetes Resources. Harness can create scaffolding around Kubernetes Resources removing complexities around crafting your own resource definitions that are purpose made for deployments. Harness can offer granular deployment lifecycle support around different Kubernetes Resources supporting canary and blue/green deployments inside Kubernetes.

#  Why is Canary deployment tricky with EKS deployments?

Canary Deployments are a progressive delivery pattern for rolling out releases to a subset of users.  Canary Deployments can be complex because of the multiple phases and the judgment call of when to promote or rollback a canary. The Harness Platform has smart verification taking away the manual toil in verification and enables seamless Canary Deployments. 



