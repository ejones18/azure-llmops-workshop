---
title: 'Lab 05: Automating everything'
layout: default
nav_order: 5
---

#### Activating LLMOps - automating everything

In this lab, we will build atop of the concepts covered in the previous labs to create a sample LLMOps workflow using an example PromptFlow.

The focus will be on building out two example pipelines that test an orchestration flow when changes have been made in a PR, run an evaulation flow for said orchestration flow before awaiting manual approval for the flow to be approved to a web app.

#### Prerequisites

- An Azure OpenAI resource, within which there is a GPT-35-Turbo PAYGO model deployed called `GPT-35-Turbo`,
- An Azure AI Hub, within which there is an AI project - the project will need the `Reader` RBAC role over the Hub's associated storage account. As well as this, the above Azure OpenAI resource should be added as connection to the Hub - the connection should be called `aoai`,
- An Azure Container Registry resource,
- A service principle with the owner role at the subscription scope - see [here](https://learn.microsoft.com/en-us/cli/azure/azure-cli-sp-tutorial-1?tabs=bash#create-a-service-principal-with-role-and-scope). Note, the output of this will need to be used later when creating the service connection in Azure DevOps,
- An Azure DevOps organisation and project. Note that new organisations will need to request a free gran of parallel jobs as per [here](https://learn.microsoft.com/en-us/azure/devops/pipelines/licensing/concurrent-jobs?view=azure-devops&tabs=ms-hosted#microsoft-hosted-cicd),
- VS Code and Git installed locally.

#### Setup