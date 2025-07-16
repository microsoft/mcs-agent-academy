# 🚨 Mission 03: Deploy a Declarative Agent for Microsoft 365 Copilot

### 🕵️‍♂️ CODENAME: `OPERATION COPILOT EXTENSION`

> **⏱️ Operation Time Window:** `~60 minutes`

## 🎯 Mission Brief:

Welcome to your first field assignment, Agent Maker. You’ve been selected to design, equip, and deploy a Declarative Agent—a specialized operative embedded directly into Microsoft 365 Copilot and Teams.

Unlike traditional agents, declarative agents operate with a defined mission (instructions), tools (prompts/connectors), and strategic access to internal intelligence (knowledge sources like SharePoint, Dataverse, and more). Your job is to build this agent using Microsoft Copilot Studio—a no-code command center where your agent’s skills and purpose come to life.

Let’s go.

## 🔎 Objectives

- [What is a declarative agent for Microsoft 365 Copilot?](#️-what-is-a-declarative-agent-for-microsoft-365-copilot)
- [Why would I use Microsoft Copilot Studio to build a declarative agent?](#-why-would-i-use-microsoft-copilot-studio-to-build-a-declarative-agent)
  - [Feature comparison](#feature-comparison)
  - [Extending Microsoft 365 Copilot with declarative agents built in Copilot Studio](#extending-microsoft-365-copilot-with-declarative-agents-built-in-copilot-studio)
- [Lab 03: Build a declarative agent in Microsoft Copilot Studio for Microsoft 365 Copilot](#-lab-03-build-a-declarative-agent-in-microsoft-copilot-studio-for-microsoft-365-copilot)
  - [Understanding Business-to-Employee (B2E)](#-understanding-business-to-employee-b2e)
  - [Use case scenario](#-use-case-scenario)
  - [Prerequisites](#prerequisites)
  - [3.1 Create a declarative agent](#31-create-a-declarative-agent)
  - [3.2 Create and add a prompt for your declarative agent](#32-create-and-add-a-prompt-for-your-declarative-agent)
  - [3.3 Update instructions and test your declarative agent](#33-update-instructions-and-test-your-declarative-agent)
  - [3.4 Publish your declarative agent to Microsoft 365 Copilot and Teams](#34-publish-your-declarative-agent-to-microsoft-365-copilot-and-teams)
- [Mission Complete](#-mission-complete)
- [Tactical Resources](#-tactical-resources)

## 🕵🏻‍♀️ What is a declarative agent for Microsoft 365 Copilot?

Declarative agents are tailored versions of Microsoft 365 Copilot. You can customize Microsoft 365 Copilot to meet specific business needs by providing it with instructions to support a particular process, ground it with enterprise knowledge, and leverage tools for wider extensibility. This allows organizations to create personalized experiences with greater functionality for their users.

## 🤔 Why would I use Microsoft Copilot Studio to build a declarative agent?

As a maker, there's a chance you've already explored [Copilot Studio agent builder](https://learn.microsoft.com/microsoft-365-copilot/extensibility/copilot-studio-agent-builder?WT.mc_id=power-172614-ebenitez) in Microsoft 365 Copilot and so you're probably wondering _why build a declarative agent in Microsoft Copilot Studio?_

Microsoft Copilot Studio offers a comprehensive set of tools and features for declarative agents that go beyond the limitations of Copilot Studio agent builder. Similar to Copilot Studio agent builder, you don't need to know programming or software development to build in Microsoft Copilot Studio. Let's break this down further to understand the differences between Copilot Studio Agent Builder and Copilot Studio for building declarative agents.

### Feature comparison

The following table highlights the differences when building a declarative agent in Copilot Studio agent builder and Copilot Studio.

| Feature                   | Copilot Studio agent builder in Microsoft 365 Copilot                          | Extend Microsoft 365 Copilot in Copilot Studio                                |
|---------------------------|-------------------------------------------------------|------------------------------------------------------------|
| **Knowledge**       | Web, SharePoint, Teams chats, Outlook emails, Copilot connectors     | Web search (via Bing), SharePoint, Dataverse, Dynamics 365, Copilot connectors  |
| **Tools**       | Code interpreter, image generator     | 1400+ Power Platform connectors, custom connectors, prompt, computer use, REST API, Model Context Protocol   |
| **Starter prompts**         | Configure prompts for users to get started quickly   | Configure prompts for users to get started quickly  |
| **Channel**           | Agent only published to Microsoft 365 Copilot     | Agent published to Microsoft 365 Copilot and Teams      |
| **Sharing permissions**         | Users are only viewers    | Users can be editors or viewers   |

There are more capabilities offered for declarative agents built in Microsoft Copilot Studio which we'll learn about next.

> - To learn more about Copilot Studio agent builder, head to [Copilot Developer Camp: Lab MAB1 - Build your first agent](https://microsoft.github.io/copilot-camp/pages/make/agent-builder/01-first-agent/)
> - For pro-development of extending a declarative agent beyond Copilot Studio agent builder for Microsoft 365 Copilot, head to [Copilot Developer Camp: Lab MAB1 - Build your first agent](https://microsoft.github.io/copilot-camp/pages/extend-m365-copilot/)

### Extending Microsoft 365 Copilot with declarative agents built in Copilot Studio

Let's expand what we've learnt from the feature comparison table.

#### Customization

- **Detailed Instructions**: You can provide detailed instructions and capabilities to define the agent's purpose and behavior precisely.
  - This includes invoking tools simply from using natural language.

- **Enterprise Knowledge Access**: Enables access to enterprise knowledge that respect user permissions.
  - SharePoint integration
  - Dataverse integration
  - Dynamics 365 integration
  - Microsoft 365 Copilot connectors enabled by your organization administrator

   ![Customization](assets/3.0_01_Customization.png)

#### Advanced Capabilities

- **Integration with External Services**: Allows you to choose from 1400+ Power Platform connectors that integrate with external services, providing more complex and powerful functionalities.
  - Examples include [docusign](https://learn.microsoft.com/connectors/docusign/?WT.mc_id=power-172614-ebenitez), [ServiceNow](https://learn.microsoft.com/connectors/service-now/?WT.mc_id=power-172614-ebenitez), [Salesforce](https://learn.microsoft.com/connectors/salesforce/?WT.mc_id=power-172614-ebenitez), [SAP](https://learn.microsoft.com/connectors/sap/?WT.mc_id=power-172614-ebenitez) and more
  - Alternatively, you can also leverage Model Context Protocol servers and REST APIs directly within your declarative agent

- **AI prompts**: Use a prompt to analyze and transform text, documents, images and data with natural language and AI reasoning.
  - Select the chat model, choose from Basic (Default), Standard, Premium
  - Option to bring-your-own Azure AI Foundry model to ground your prompt in

- **More deployment configuration options**: Select channels and define user permissions.
  - Publish to Teams, a familiar user interface for your users for quicker adoption
  - Edit user permissions can be shared to prevent a single point of dependency on the owner of the agent

   ![Customization](assets/3.0_02_AdvancedCapabilities.png)

In summary, declarative agents in Microsoft Copilot Studio allow customization of Microsoft 365 Copilot to suit business needs through integration of enterprise knowledge systems, tools to connect to external services or AI GPT models.

## 🧪 Lab 03: Build a declarative agent in Microsoft Copilot Studio for Microsoft 365 Copilot

We'll next learn how to build a declarative agent for a "Business-to-Employee" use case which will act as an **IT helpdesk agent**.

- [3.1 Create a declarative agent](#31-create-a-declarative-agent)
- [3.2 Create and add a prompt for your declarative agent](#32-create-and-add-a-prompt-for-your-declarative-agent)
- [3.3 Update instructions and test your declarative agent](#33-update-instructions-and-test-your-declarative-agent)
- [3.4 Publish your declarative agent to Microsoft 365 Copilot and Teams](#34-publish-your-declarative-agent-to-microsoft-365-copilot-and-teams)

> [!NOTE]
> This lab will outline steps to add a Prompt as a tool. The following lessons will dive into adding knowledge sources and adding other tools available. Keeping it simple for your learning 😊
> [!CAUTION]
> You do need a Microsoft 365 Copilot user license to publish your declarative agent built in Copilot Studio to Microsoft 365 Copilot.

### 👩🏻‍💼 Understanding Business-to-Employee (B2E)

Business-to-Employee (B2E) refers to the interactions and services that a business provides directly to its employees. In the context of an agent, it means using the advanced capabilities of Copilot Studio to support and enhance the work experience of employees within the organization.

### ✨ Use case scenario

**As an** employee

**I want to** get quick and accurate help from the IT helpdesk agent for issues like device problems, network troubleshooting, printer setup

**So that I can** stay productive and resolve technical issues without delays

Let's begin!

### Prerequisites

- Users and makers must have a license to use Microsoft 365 Copilot.
- Makers must have permissions to create in and have access to a Copilot Studio environment.

### 3.1 Create a declarative agent

1. Navigate to [https://copilotstudio.microsoft.com/](https://copilotstudio.microsoft.com/) and sign in using your credentials. Make sure to switch to your environment that you're using for these labs.

1. Select **Agents** from the menu and select **Copilot for Microsoft 365**.

   ![Copilot for Microsoft 365](assets/3.1_02_CopilotForM365.png)

1. Next, we're going to create a declarative agent by selecting **+ Add** agent.

   ![Add Agent](assets/3.1_03_AddAgent.png)

1. We'll then see the conversational creation experience load where we can chat in natural language with Copilot to describe the declarative agent we want to build, and use the provided questions for guidance.

   Let's enter a detailed description that outlines the following,
   - the task of the agent
   - what type of inquiries it can handle
   - the format of its response
   - the goal of the agent

   ```
   You are a highly skilled and experienced IT professional specializing in a wide range of computer systems, networking, and cybersecurity. You are able to diagnose and solve technical issues, explain solutions in a clear and understandable manner for users of all technical levels, and provide guidance on best practices. You should be concise and informative, using step-by-step instructions with bullet points when appropriate. Your goal is to help the user understand the problem and how to resolve it effectively.
   ```

   ![Create Prompt](assets/3.1_04_CreatePrompt.png)

1. After submitting the prompt, a noticeable update will appear on the right hand side pane with the details and instructions of the agent as defined by the prompt. Next you'll be asked to confirm the name of your agent and Copilot will have suggested a name.

   Either enter `yes` to accept the suggested name or enter a different name such as the following,

   ```
   Contoso Tech Support Pro
   ```

   ![Instructions updated](assets/3.1_05_InstructionsUpdated.png)

> [!NOTE]
> The Copilot conversational creation experience can vary each time where the provided questions for guidance may be slightly different than previously.

6. The name of the agent has now been updated as seen on the right hand side pane. We're now asked to refine the instructions for the agent. The instructions on the right hand side pane is already suitable as it covers the topics we want - refer to yellow highlighted text in screenshot below. Instead, we'll expand on how it should format its response and the tone. We'll enter the following,

   ```
   Concise and Informative:
   - Bullet Points: Use bullet points for clarity and to break down information into digestible parts.
   - Summarize: Provide a brief summary of the solution at the end of the explanation.

   User-Friendly Communication:
   - Empathy: Show empathy and understanding of the user's frustration or confusion.
   - Encouragement: Encourage users by acknowledging their efforts and progress.

   Interactive and Engaging:
   - Ask for Feedback: After providing a solution, ask if the user needs further assistance or if the solution worked.
   ```

   ![Name updated](assets/3.1_06_NameUpdated.png)

7. Next we'll be asked if we want to add any publicly accessible websites or knowledge. I'll respond with `No` as we will only be adding a prompt for our declarative agent in this lab. Subsequent labs in future lessons will cover knowledge sources.

   ![No websites or knowledge sources added](assets/3.1_07_KnowledgeSources.png)

1. We'll then see a response from Copilot that we have now finished configuring our agent using the Copilot conversational creation experience. Click **Create** to provision the declarative agent for Microsoft 365 Copilot.

> [!NOTE]
> Reminder: The Copilot conversational creation experience can vary each time where the provided questions for guidance may be slightly different than previously. So you may be seeing a different message from Copilot at the end of your configuration.

   ![Create agent](assets/3.1_08_CreateDeclarativeAgent.png)

9. Once the agent has been provisioned, you'll see the details of the agent which contains the description and the instructions defined during the Copilot conversational creation experience.

   ![Agent details](assets/3.1_09_01_AgentDetails.png)

   Scroll down the pane and you'll also see the capabilities of adding knowledge, enabling web search (via Bing), starter prompts and the publish details of the declarative agent for Microsoft 365 Copilot. The starter prompts will also be displayed in the test pane on the right hand side. Users can select these starter prompts to begin interacting with the agent.

   ![Additional capabilities](assets/3.1_09_02_SuggestedPrompts.png)

1. In the Details section of the agent, you have the ability to change the agent icon as well. Select **Edit**.

   ![Edit details](assets/3.1_10_01_EditDetails.png)

   Here you can change the icon and the background color. Select **Save** and then select **Save** again to update the details of the agent.

   ![Change icon](assets/3.1_10_02_ChangeIcon.png)

1. Let's do a quick test of the agent we've created. Select one of the **Starter Prompts** in the test pane on the left hand side.

   ![Change icon](assets/3.1_11_TestUsingStarterPrompt.png)

1. Our agent will then respond. Notice how it adhered to the instructions by providing bullet points into digestible parts, and used empathy in its response.

   ![Change icon](assets/3.1_12_TestResponse.png)

   If you scroll to the bottom of the message, notice how it also asked for feedback after providing a solution as instructed.

   ![Change icon](assets/3.1_13_TestResponse.png)

In a few minutes you've added a declarative agent for Microsoft 365 Copilot in Copilot Studio 🙌🏻

Next we'll learn how to add a tool to our agent, we'll create a prompt.

### 3.2 Create and add a prompt for your declarative agent

1. Scroll down to the **Tools** section and select **+ Add tool**

   ![Add tool](assets/3.2_01_AddTool.png)

1. The Tools modal will appear and a list of Power Platform connectors is displayed. To add a Prompt, select **+ New tool**.

   ![New tool](assets/3.2_02_NewTool.png)

1. A list of other tools is displayed - Prompt, Custom connector, REST API and Model Context Protocol. If your organization meets the [requirements for Computer Use](https://learn.microsoft.com/microsoft-copilot-studio/computer-use?tabs=new#requirements/?WT.mc_id=power-172614-ebenitez), this will also appear in the list. Select **Prompt**.

   ![Select prompt](assets/3.2_03_SelectPrompt.png)

1. Enter a name for the prompt. Let's name our prompt `IT Expert`.

   ![Enter name](assets/3.2_04_NamePrompt.png)

1. Select the **chevron icon** next to the **Model** to see the different chat models you can choose from. By default, the **Basic GPT-4o mini** model is selected and you also have the option to bring-your-own-model using Azure AI Foundry Models. We'll stick with the selected default model.

   ![Change model](assets/3.2_05_ChangeModel.png)

1. Next, we'll provide our prompt with instructions. There's 3 methods that you can choose from

   - Use Copilot to generate instructions for you based on your description of what you want the prompt to do.
   - Use a preset template from the prompt library to create a prompt.
   - Manually enter your own instructions.

1. Let's first try using Copilot to generate instructions based on a description entered. Enter the following into the Copilot field and submit.

   ```
   I need an IT expert that can help answer questions related to networking, computer systems, user devices and anything else IT related
   ```

   ![Get started with Copilot](assets/3.2_07_UseCopilot_EnterPrompt.png)

1. Copilot will then begin to generate a prompt for us.

   ![Copilot drafts prompts](assets/3.2_08_CopilotDraftingPrompt.png)

1. The Copilot generated draft instructions will then appear.

   ![Copilot generated draft instructions](assets/3.2_09_CopilotGeneratedInstructions.png)

1. Scroll down to the bottom of the instructions and you'll see the user input parameter already defined by Copilot. You then have the option to
   - Keep the draft instructions generated.
   - Refresh the draft instructions using Copilot.
   - Clear the draft instructions.

   Clear the draft instructions by selecting the **trash bin** icon and we'll next try the prompt library.

   ![Prompt instructions](assets/3.2_10_Options.png)

1. Select the **prompt library** link.

   ![Select prompt library](assets/3.2_11_SelectPromptLibrary.png)

1. You'll see a list of prompt templates to choose from. These are from the [Power Platform Prompt library](https://aka.ms/power-prompts).

   ![Prompt library](assets/3.2_12_PromptLibrary.png)

1. Search for the `IT expert` prompt and select it.

   ![Select IT expert prompt](assets/3.2_13_ITExpertPrompt.png)

1. The prompt will then be added as the instructions with the input parameter as defined by the prompt template. Similar to the approach we took when providing instructions for our agent during the conversational creation experience with Copilot, this prompt template outlines
   - a task,
   - what type of inquiries it can handle,
   - and the format of its response and the goal of the prompt.

   ![Prompt instructions](assets/3.2_14_ITExpertPromptInstructions.png)

1. Clear the instructions and we'll next try manually entering the instructions. We'll use the [IT Expert prompt](https://adoption.microsoft.com/sample-solution-gallery/sample/pnp-powerplatform-prompts-it-expert/) from the [Power Platform Prompt library](https://aka.ms/power-prompts). Copy and paste the prompt.

   ```
   I want you to act as an IT Expert. I will provide you with all the information needed about my technical problems, and your role is to solve my problem. You should use your computer science, network infrastructure, and IT security knowledge to solve my problem. Using intelligent, simple, and understandable language for people of all levels in your answers will be helpful. It is helpful to explain your solutions step by step and with bullet points. Try to avoid too many technical details, but use them when necessary. I want you to reply with the solution, not write any explanations. My problem is [Problem]
   ```

   ![Prompt instructions](assets/3.2_15_PromptInstructions.png)

1. Next, we can define the user input parameters of our prompt. These can be text and images, and sample data to test with. There's also the capability to ground the prompt with knowledge from Dataverse tables. For this exercise, we only have one user input to define which is the problem input. This is currently a placeholder in our prompt as `[Problem]`. We'll now configure this input either by entering the `/` character or selecting **+Add content** and then select **Text**.

   ![Text input](assets/3.2_16_AddContent.png)

1. We can now enter a name for our input parameter and sample data.

   Enter the following as the name

   ```
   problem input
   ```

   Enter the following as the sample data

   ```
   My laptop gets an error with a blue screen
   ```

   Then select **Close**.

   ![Configure problem input](assets/3.2_17_NameSampleData.png)

1. The problem input parameter will now be added to the instructions with the configured sample data. We can now test our prompt!

   ![Problem input added](assets/3.2_18_InputAdded.png)

1. Select **Test** to the test the prompt.

   ![Test instructions](assets/3.2_19_Test.png)

1. The response will then display. Notice how the response provides headings with bullet points as per the instructions. Scroll down and review the remainder of the model response.

   ![Model response](assets/3.2_20_ModelResponse.png)

1. Before we save our prompt, let's learn about the settings that can be configured for this prompt. Select the **ellipsis (...) icon**.

   ![Prompt settings](assets/3.2_21_Settings.png)

1. Here we'll see three settings that can be configured.

   - **Temperature**: Lower temperatures lead to predictable results, while higher temperatures allow more diverse or creative responses.
   - **Record retrieval**: Specify the number of records retrieved for your knowledge sources.
   - **Include links in the response**: When selected, the response includes link citations for the retrieved records.

   Select the **X** icon to exit from Settings.

   ![Configure settings](assets/3.2_22_ConfigureSettings.png)

1. Select **Save** to save the prompt.

   ![Save prompt](assets/3.2_23_SavePrompt.png)

1. Next, select **Add to agent** to add the prompt to our declarative agent.

   ![Prompt instructions](assets/3.2_24_AddToAgent.png)

1. The prompt will now appear under Tools 🙌🏻

   ![Prompt added](assets/3.2_25_PromptAdded.png)

We'll next update our instructions to invoke the prompt and test our declarative agent.

### 3.3 Update instructions and test your declarative agent

1. Scroll up to the **Details** section and select **Edit**. This will enable the fields to be editable.

   ![Select Edit](assets/3.3_01_EditInstructions.png)

1. We can now update our instructions to invoke our prompt by referencing the name of the prompt. Clear the instructions, then copy and paste the following.

   ```
   - When a user asks questions about their device, run the "IT Expert" prompt. Use their question as the problem input of the "IT Expert" prompt.
   ```

   Notice how the final sentence is instructing the agent to use the question asked by the user as the value for the problem input parameter. The agent will use the question as the problem input for the prompt. Next, select **Save**.

   ![Update instructions to invoke prompt](assets/3.3_02_UpdateInstructionsWithPrompt.png)

1. We're now ready to test our updated instructions of our declarative agent. Select the **refresh icon** in the test pane.

   ![Select refresh icon](assets/3.3_03_RefreshTestPane.png)

1. Next, enter the following prompt below and submit.

   ```
   Can you help me, my laptop is encountering a blue screen
   ```

   ![Perform test](assets/3.3_04_PerformTest.png)

1. The agent invokes the prompt and responds, with a citation to the agent.

   ![Prompt instructions](assets/3.3_05_ModelResponse.png)

Let's now publish our declarative agent 😃

### 3.4 Publish your declarative agent to Microsoft 365 Copilot and Teams

1. Select **Publish**.

> [!IMPORTANT]
> Reminder: To publish a declarative agent built in Copilot Studio to Microsoft 365 Copilot and Teams, you need a Microsoft 365 Copilot user license.

   ![Publish agent](assets/3.4_01_PublishAgent.png)

2. A modal will appear which displays the Channels and publishing details that can be updated.

   - Channels: The agent will be published to Microsoft 365 Copilot and Microsoft Teams.
   - Agent app information: This is what will be displayed when the user adds the agent to Microsoft 365 Copilot or in Microsoft Teams. These are fields that can be updated as needed. For example, you can update the **Short description**, **Long description**, **Developer name** with your name.

> [!TIP]
> If you don't see all the fields displayed on your browser, try zooming out e.g. 75%

   ![Agent app details](assets/3.4_02_ConfigurePublishingAgentDetails.png)

3. Select **Publish**. Copilot Studio will then begin publishing the agent.

   ![Publishing agent](assets/3.4_03_PublishingAgent.png)

1. When publishing is completed, we'll see the [Availability options](https://learn.microsoft.com/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions#set-availability-options/?WT.mc_id=power-172614-ebenitez) of the agent.

   | Availability option    | Description |
   | ---------- | ---------- |
   | Share Link | Copy the link to distribute it with shared users to open the agent in Microsoft 365 Copilot |
   | Show to my teammates and shared users  | Lets you grant access to others to participate in authoring the agent, or to security groups to grant them access to use the agent in Microsoft 365 Chat or Teams.  |
   | Show to everyone in my org   | Submit to the tenant admin to add to the organizational catalog for all tenant users to add the agent. The agent will show under Built by your org in Microsoft 365 Copilot and in Teams    |
   | Download as a .zip    | Download as a zip file to upload as a custom app in Teams    |

   ![Availability options](assets/3.4_04_AvailabilityOptions.png)

1. Let's take a look at sharing the agent. Select **Show to my teammates and shared users**. A pane will appear where you can search for users you want to to share the agent with either by entering their name, an email or a security group. You can review this list anytime to edit who has access to the agent.

   There's also two checkboxes:
   - _Send an email invitation to new users_ - new users will receive an email invitation.
   - _Visible Built with Power Platform_ - agent becomes available in the Built with Power Platform section of the Teams app store.

   For more details, refer to [Connect and configure an agent for Teams and Microsoft 365](https://learn.microsoft.com/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams/?WT.mc_id=power-172614-ebenitez).

   Select **Cancel** or the **X** icon to exit from the pane.

   ![Share agent](assets/3.4_05_ShareAgent.png)

1. Select **Copy** and in a new browser tab, paste the link.

   ![Copy link](assets/3.4_06_CopyLink.png)

1. Microsoft 365 Copilot will load and a modal will appear with the agent app details.
   Notice how the developer name, the short description and long description is displayed. These are from the publishing details updated in an earlier step.

   Select **Add**.

   ![Availability options](assets/3.4_07_AgentAppDetails.png)

1. Our declarative agent will load next. We can see the starter prompts to select from which quickly enables users to seek immediate help.

   Let's select the **Hardware Problem** prompt which will automatically prepopulate the message Copilot field. Submit the question to Copilot.

   ![Select starter prompt](assets/3.4_08_SelectStarterPrompt.png)

1. The agent will then invoke our **IT Expert** prompt and we'll see the model response returned as a message in our declarative agent.

   ![Response](assets/3.4_09_Response.png)

1. But _how do we know_ the declarative agent invoked the prompt? 👀 Well, here's a tip!

> [!TIP]
> You can test and debug agents in Microsoft 365 Copilot by enabling [developer mode](https://learn.microsoft.com/microsoft-365-copilot/extensibility/debugging-copilot-agent#use-developer-mode-in-copilot-chat/?WT.mc_id=power-172614-ebenitez).

   Enter the following in the message Copilot field and submit.

   ```
   -developer on
   ```

   A confirmation message will appear to let you know developer mode is now enabled.

   ![Developer mode enabled](assets/3.4_10_DeveloperModeEnabled.png)

10. Submit the following question to invoke the prompt.

      ```
      Can you help me, my laptop is encountering a blue screen
      ```

      ![Enter question](assets/3.4_11_EnterQuestion.png)

11. We'll see a model response from our **IT Expert** prompt again returned as a message. Scroll down to the bottom of the message and a card with debug information is displayed. 

      Expand **Agent Debug Info** by selecting it.

      ![Agent debug info](assets/3.4_12_AgentDebugInfo.png)

12. Here you'll find information on the agent metadata that occured at runtime. In our use case, we'll be focusing on the _Actions_ section

   - **Matched actions** highlight the current status of functions found during the app's search.
   - **Selected actions** highlight the current status of functions chosen to run based on the app's decision-making process.

      So here we can see the agent orchestrator chose to invoke the IT Expert prompt as per the instructions of our declarative agent. This is further outlined in the _Executed Actions_ section which also tells us that it successfully invoked the prompt.

      ![Review agent debug info](assets/3.4_13_ReviewAgentDebugInfo.png)

13. To turn off developer mode, enter the following in the message Copilot field and submit.

      ```
      -developer off
      ``` 
      A confirmation message will appear to let you know developer mode is disabled. Cool, now you know how to verify whether your declarative agent in Microsoft 365 Copilot invoked your prompt 🌞

      ![Developer mode disabled](assets/3.4_14_DeveloperModeDisabled.png)

14. We'll now test our agent in Microsoft Teams. Navigate to **Apps** using the left hand side menu and select **Teams** under the _Apps_ section.

      ![Select Teams in Apps](assets/3.4_15_NavigateToApps.png)
   
15. Teams will then load in a new browser tab and you'll see Microsoft 365 Copilot load by default, with the right hand side pane listing all of your available agents, including the **Contoso Tech Support Pro** declarative agent.

      ![Microsoft 365 Copilot in Teams](assets/3.4_16_CopilotAgentsInTeams.png)

16. Select **Apps** on the left hand side menu. Either search for **Contoso Tech Support Pro** or scroll down and select the agent.

      ![Select agent from Apps](assets/3.4_17_SelectAgentFromApps.png)

17. We'll then see our agent load. The agent can be pinned to the menu by right clicking on the app and select **Pin**.

      ![Pin agent](assets/3.4_18_PinAgent.png)

18. Let's next test our agent. Enter the following prompt and submit.

      ```
      Can you help me, my laptop is encountering a blue screen
      ```

      ![Pin agent](assets/3.4_19_EnterPrompt.png)

19. A model response from our prompt will then be displayed.

      ![Response in Teams](./assets/3.4_20_AgentInTeams.png)

In a few minutes, you've learnt how to publish your declarative agent and test it in Microsoft 365 Copilot and in Teams 😊

## ✅ Mission Complete

Congratulations! 👏🏻 You've built a declarative agent in Copilot Studio where you added a Prompt, instructed the agent to use the Prompt and how to test + publish your agent to Microsoft 365 Copilot and Teams.

Your agent is now active duty—ready to assist, troubleshoot, and serve internal users on-demand.

This is the end of **Lab 03 - Build a declarative agent in Microsoft Copilot Studio for Microsoft 365 Copilot**, select the link below to move to the next lesson.

⏭️ [Move to **Creating a new Solution** lesson](/04-creating-a-solution/README.md)

Until next time, stay sharp. The future of enterprise work runs through agents—and now you know how to build one.

## 📚 Tactical Resources

🔗 [Build declarative agent in Microsoft Copilot Studio for Microsoft 365 Copilot](https://learn.microsoft.com/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext/?WT.mc_id=power-172614-ebenitez)

🔗 [Add prompts](https://learn.microsoft.com/ai-builder/create-a-custom-prompt?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext/?WT.mc_id=power-172614-ebenitez)

🔗 [Share agents with other users](https://learn.microsoft.com/microsoft-copilot-studio/admin-share-bots/?WT.mc_id=power-172614-ebenitez)

📺 [Build prompts for your agent](https://aka.ms/ai-in-action/copilot-studio/ep3)

![mcs-agent-academy-recruit-03](https://m365-visitor-stats.azurewebsites.net/?resource=https://github.com/microsoft/mcs-agent-academy-recruit/tree/main/03-create-a-declarative-agent-for-M365Copilot)
