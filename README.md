# How I Deployed Azure Infrastructure Using ARM Templates Written in Bicep
Overview

This repository documents how I deployed Azure infrastructure using Infrastructure as Code (IaC) by writing Bicep templates that compile into ARM templates.

Instead of manually deploying resources through the Azure Portal, the entire infrastructure was defined in code and deployed using Azure Resource Manager.

This project simulates a real world scenario where a financial institution needed to deploy new infrastructure to support a product release.

## Scenario

Capitec needed to release a new digital banking feature that required scalable and reliable cloud infrastructure.

To support this release, the infrastructure needed to include:

✅ Load Balancers to distribute application traffic

✅ Storage Accounts to support application data

✅ Virtual Networking for secure communication

✅ Supporting Azure infrastructure resources


The requirement was to deploy the infrastructure in a repeatable and scalable way, avoiding manual configuration through the Azure portal.

For this reason, the infrastructure was deployed using Bicep templates compiled into ARM templates.

# Architecture Design

The following diagram shows the architecture used in this deployment.

<p align="center">
  <img src="images/AZ104 - Diagram.drawio.png" width="750">
</p>

How I Deployed the Infrastructure

To deploy the infrastructure, I used the Azure CLI together with Bicep templates.

Using the Azure CLI allowed me to:

✅ Deploy resources in bulk
✅ Automate the deployment process
✅ Reduce the risk of manual configuration errors
✅ Deploy infrastructure using Infrastructure as Code (IaC)

Instead of manually provisioning resources in the Azure Portal, I defined the infrastructure in Bicep, which compiles into ARM templates that Azure Resource Manager uses to deploy resources.

# Step 1 — Define the Infrastructure Requirements

Before writing any code, I first defined the infrastructure components required for the deployment.

This project simulates a scenario where a financial institution needs scalable cloud infrastructure to support a new digital banking feature.

Based on this requirement, the infrastructure needed to include the following Azure resources:

✅ Virtual Network for secure communication between services

✅ Load Balancer to distribute application traffic

✅ Storage Accounts for application data

✅ Supporting Azure infrastructure components

Once the infrastructure requirements were defined, I began writing the Bicep template that describes the entire environment.

# Step 2 — Define Infrastructure Using Bicep

After defining the required infrastructure components, I created a Bicep template to describe the Azure resources.

Bicep provides a simplified syntax for defining Azure infrastructure, while still compiling into ARM templates, which Azure Resource Manager uses for deployments.

In my main.bicep template, I defined the resources required for the environment including:

✅ Virtual network configuration

✅ Storage accounts

✅ Load balancing resources

✅ Supporting Azure infrastructure components

By defining these resources in code, the infrastructure can be version controlled and redeployed consistently across environments.

# Step 3 — Authenticate with Azure

Once the infrastructure template was ready, I authenticated with Azure using the Azure CLI.

This allows the CLI to interact with Azure Resource Manager and execute deployment commands.

az login

After logging in, I verified the active subscription.

az account show

If multiple subscriptions were available, I selected the correct one.

az account set --subscription "SUBSCRIPTION_ID"

This ensures that the deployment is executed within the correct Azure environment.



# Step 4 — Create the Resource Group

Next, I created a resource group that would contain all resources associated with the deployment.

Resource groups allow Azure resources to be logically grouped and managed together.

az group create \
--name capitec-banking-rg \
--location southafricanorth

This resource group acts as the container where the infrastructure will be deployed.



# Step 5 — Compile the Bicep Template

Bicep templates are compiled into ARM templates before deployment.

Although Azure performs this step automatically during deployment, the template can also be compiled manually.

az bicep build --file main.bicep

This command converts the Bicep file into the equivalent ARM template JSON file used by Azure Resource Manager.



# Step 6 — Deploy the Infrastructure

Once the template was ready, I deployed the infrastructure using the Azure CLI.

az deployment group create \
--resource-group capitec-banking-rg \
--template-file main.bicep

During this step, Azure Resource Manager processes the compiled ARM template and provisions the infrastructure automatically.

Azure Resource Manager ensures that:


✅ Resources are deployed in the correct order

✅ Dependencies between resources are resolved automatically

✅ Infrastructure is deployed consistently

This allows complex infrastructure environments to be deployed reliably using code.



# Step 7 — Verify the Deployment

After the deployment completed successfully, I verified that the infrastructure resources were created.

az resource list \
--resource-group capitec-banking-rg \
--output table

This command lists all resources within the resource group and confirms that the infrastructure was successfully deployed.

# Why I Used Azure CLI for Deployment

In this project, I intentionally used the Azure CLI instead of manually deploying resources through the Azure Portal.

Manual deployments can introduce inconsistencies and configuration drift between environments.

Using Bicep templates and the Azure CLI allows infrastructure to be deployed in a way that is:

✅ Repeatable

✅ Automated

✅ Scalable

✅ Consistent across environments

This approach reflects modern cloud engineering and DevOps practices, where infrastructure is managed using code rather than manual configuration.

Key Takeaways

Through this project, I demonstrated the following cloud engineering practices.

✅ Deploying Azure infrastructure using Infrastructure as Code

✅ Writing Bicep templates that compile into ARM templates

✅ Automating infrastructure deployment using the Azure CLI

✅ Structuring infrastructure for scalable and repeatable deployments

✅ Simulating a real world financial services cloud deployment scenario
