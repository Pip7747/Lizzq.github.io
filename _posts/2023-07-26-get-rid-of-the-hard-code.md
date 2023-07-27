---
title: How I Improved Our Jenkins File
layout: post
categories: [Lizz,study]
tags: [Jenkins，Vault]
---


# Using Vault for Credential Management and Global Credentials

## Introduction

During my internship as a DevOps engineer, I had the opportunity to work on our Jenkins pipeline, specifically the Jenkinsfile used for our CI/CD processes. One day, a senior DevOps engineer asked me to make some changes to our Jenkinsfile to improve security and avoid hardcoding sensitive credentials. This was an essential task to ensure our CI/CD pipeline adheres to best practices and maintains a higher level of security.

In this article, I'll walk you through the changes I made to the Jenkinsfile, using HashiCorp Vault for credential management and global credentials in Jenkins.

## The Problem: Hardcoding Credentials

Before the changes, our Jenkinsfile had some hardcoded credentials, such as AWS access keys, Docker registry credentials, and SSH keys. This practice was insecure and could potentially lead to security breaches if these credentials were ever exposed.

**Solution: Using HashiCorp Vault**

To address the security concerns, I integrated HashiCorp Vault into our Jenkins pipeline to manage our sensitive credentials securely. Vault is a powerful tool that allows us to store, rotate, and access secrets like API keys, passwords, and certificates.

### Installation and Configuration

The first step was to install and configure HashiCorp Vault on our Jenkins server. Once Vault was up and running, I created a Vault credential in Jenkins, which included the Vault URL and authentication token. This token provides the necessary permissions to access the secrets stored in Vault.

### Storing Credentials in Vault

With the Vault credential set up, I modified our Jenkinsfile to retrieve credentials from Vault instead of hardcoding them directly. For example, instead of having the AWS access keys hardcoded, we now store them in Vault under a specific path, such as `secret/aws/aws_prod`.

**Code Example:**

```markdown
def vaultPath = "secret/aws/aws_prod"

def createInvalidation() {
  withVault(configuration: [timeout: 60, vaultCredentialId: 'Vault Credential', vaultUrl: 'https://vault.jiangren.com.au'], vaultSecrets: [[path: vaultPath, secretValues: [[vaultKey: 'AWS_ACCESS_KEY_ID'], [vaultKey: 'AWS_SECRET_ACCESS_KEY']]]]) {
    sh "aws ${AWS_CLI_OPTS} cloudfront create-invalidation --distribution-id ${DISTRIBUTION_ID} --paths ${PATHS_TO_INVALIDATE}"
  }
}
```

## Using Global Credentials

Another improvement I made was to utilize global credentials in Jenkins. Global credentials allow us to define credentials once and use them across multiple Jenkins jobs and pipelines. This simplifies the management of credentials and ensures consistent usage.

In Jenkins, I configured global credentials for AWS, Docker registry, and other services we use in our CI/CD processes. Then, I updated the Jenkinsfile to reference these global credentials rather than having individual credentials hardcoded in each job.

**Code Example:**

```markdown
pipeline {
  // Use global credentials for AWS, Docker, etc.
}
```

## Conclusion

By using HashiCorp Vault for credential management and global credentials in Jenkins, we significantly improved the security and maintainability of our CI/CD pipeline. Avoiding hardcoded credentials reduces the risk of exposing sensitive information and enhances the overall security posture of our CI/CD processes. The integration of Vault and global credentials in Jenkins simplifies credential management, ensuring a smoother and more secure CI/CD workflow.