---
lab:
    title: 'Explore Azure OpenAI Service'
---

# Explore Azure OpenAI

Azure OpenAI Service brings the generative AI models developed by OpenAI to the Azure platform, enabling you to develop powerful AI solutions that benefit from the security, scalability, and integration of services provided by the Azure cloud platform.

In this exercise, you'll explore Azure OpenAI Service and use it to deploy and experiment with generative AI models.

This exercise will take approximately **25** minutes.

## Before you start

You will need an Azure subscription that has been approved for access to the Azure OpenAI service for both text and code models, and DALL-E image generation models.

- To sign up for a free Azure subscription, visit [https://azure.microsoft.com/free](https://azure.microsoft.com/free).
- To request access to the Azure OpenAI service, visit [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Provision an Azure OpenAI resource

Before you can use Azure OpenAI models, you must provision an Azure OpenAI resource in your Azure subscription.

1. Sign into the [Azure portal](https://portal.azure.com).
2. Create an **Azure OpenAI** resource with the following settings:
    - **Subscription**: *An Azure subscription that has been approved for access to the Azure OpenAI service.*
    - **Resource group**: *Choose an existing resource group or create a new one with a name of your choice.*
    - **Region**: East US\*
    - **Name**: *A unique name of your choice*
    - **Pricing tier**: Standard S0

    > \* Different regions have different availability and quota for models. In this exercise, you'll be using a GPT-35-Turbo model for text generation and a DALL-E model for image generation, both of which are suppoprted in East US. 

3. Wait for deployment to complete. Then go to the deployed Azure OpenAI resource in the Azure portal.

## Explore Azure OpenAI Studio

You can deploy, manage, and explore models in your Azure OpenAI Service by using Azure OpenAI Studio.

1. On the **Overview** page for your Azure OpenAI resource, use the **Explore** button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to [Azure OpenAI Studio](https://oai.azure.com/) directly.


1. View the pages available in the pane on the left. You can always return to the home page at the top. Additionally, OpenAI Studio provides multiple pages where you can:
    - Experiment with models in a *playground*.
    - Manage model deployments and data.

## Deploy a model for language generation

To experiment with natural language generation, you must first deploy a model.

1. On the **Models** page view the available models in your Azure OpenAI service instance.
1. Select any of the **gpt-35-turbo** models for which the **Deployable** status is **Yes**, and then select **Deploy**:


1. Create a new deployment with the following settings:
    - **Model**: gpt-35-turbo
    - **Model version**: Auto-update to default
    - **Deployment name**: *A unique name for your model deployment*
    - **Advanced options**
        - **Content filter**: Default
        - **Deployment type**: Standard
        - **Tokens per minute rate limit**: 5K\*
        - **Enable dynamic quota**: Enabled

    > \* A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.

## Use the *Chat* playground to work with the model

Now that you have deployed a model, you can use it in the *Chat* playground to generate natural language output from prompts that you submit in a chat interface.

1. In [Azure OpenAI Studio](https://oai.azure.com/), navigate to the **Chat** playground in the left pane.

    The *Chat* playground provides a chatbot interface with which you can interact with your deployed model, as shown here:


1. In the **Configuration** pane, ensure that your model deployment is selected.
1. In the **Assistant setup** pane, select the **Default** system message template, and view the system message this template creates. The system message defines how the model will behave in your chat session.
1. In the **Chat session** section, enter the following user message.

    ```
   What is generative AI?
    ```

1. Observe the output returned by the model, which should provide a definition of generative AI.
1. Enter the following user message as a follow-up question:

    ```
   What are three benefits it provides?
    ```

1. Review the output, noting that the chat session has kept track of the previous input and response to provide context (so it correctly interprets "it" as referring to "generative AI") and that it provides a suitable response based on what was requested (it should return three benefits of generative AI).

## Use the *DALL-E* playground to generate images

In addition to language generation models, Azure OpenAI Service supports the DALL-E 2 model for image generation.

> **Note**: You must have applied for and received access to DALL-E functionality in your Azure OpenAI service access application to complete this section of the exercise.

1. In [Azure OpenAI Studio](https://oai.azure.com/), navigate to the **DALL-E** playground in the left pane.
1. Enter the following prompt:

    ```
    A robot eating spaghetti
    ```

1. Select **Generate** and view the results, which should consist of an image based on the description you provided in the prompt

1. Generate a second image by modifying the prompt to:

    ```
    A robot eating spaghetti in the style of Rembrandt
    ```
1. Verify that the new image matches the requirements of the prompt

## Clean up

When you're done with your Azure OpenAI resource, remember to delete the deployment or the entire resource in the [Azure portal](https://portal.azure.com/?azure-portal=true).
