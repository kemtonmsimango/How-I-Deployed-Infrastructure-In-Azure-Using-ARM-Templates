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

Example:

How I Deployed the Infrastructure

The deployment followed these steps.

1️⃣ Define Infrastructure Using Bicep

✅ Wrote Bicep templates to define Azure resources
✅ Structured the templates to represent the required infrastructure components
✅ Used Infrastructure as Code to avoid manual configuration

Bicep provides a cleaner syntax while still compiling into ARM templates for Azure Resource Manager deployments.

2️⃣ Organize Infrastructure Code

To improve maintainability, the infrastructure code was separated into logical components.

Example components included:

✅ Networking configuration
✅ Storage resources
✅ Load balancing configuration

This modular approach makes infrastructure easier to manage and update.

3️⃣ Compile Bicep to ARM Templates

During deployment, Bicep templates are compiled into ARM templates.

✅ Bicep simplifies template development
✅ Azure Resource Manager processes the compiled templates
✅ Resources are provisioned automatically

Architecture Design

The following diagram shows the architecture used for this deployment.

(Insert architecture diagram here)

Example:
