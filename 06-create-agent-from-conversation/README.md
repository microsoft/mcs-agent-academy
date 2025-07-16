# 🚨 Mission 06: Create a custom agent using natural language with Copilot and grounding it with your data

### 🕵️‍♂️ CODENAME: `OPERATION AGENT FORGE`

> **⏱️ Operation Time Window:** `~75 minutes`

## 🎯 Mission Brief:

Welcome back, Agent Maker. This mission puts you in the command seat of the most powerful capability in Copilot Studio—creating a custom agent from scratch using only natural language… and supercharging it with your own data.

This isn’t just another chatbot. You’re building a knowledge-empowered digital coworker—one that can reason, respond, and reference real enterprise info.

Your weapon of choice? Natural language. Your mission? Design, train, and test a fully customized helpdesk agent that answers IT questions using SharePoint, uploaded files, or company URLs.

Let’s build your agent from the ground up.

## 🔎 Objectives

- [What is a custom agent?](#-what-is-a-custom-agent)
  - [What can a custom agent do?](#-what-can-a-custom-agent-do)
  - [Why use a custom agent?](#--why-use-a-custom-agent)
  - [Example](#-example)
- [Use natural language to create agents](#️-use-natural-language-to-create-agents)
- [But I'm new to "describing what I want" - what do I do?](#-but-im-new-to-describing-what-i-want---what-do-i-do)
  - [Why Prompts matter](#-why-prompts-matter)
  - [Tips for writing a good prompt](#-tips-for-writing-a-good-prompt)
  - [Example](#-example-1)
- [OK, I've created my agent... how do I ground it with knowledge?](#-ok-ive-created-my-agent-how-do-i-next-ground-it-with-knowledge)
  - [What is generative orchestration in the context of agents?](#-what-is-generative-orchestration-in-the-context-of-agents)
  - [Why knowledge sources matter?](#-why-knowledge-sources-matter)
  - [Example](#-example-2)
- [Types of knowledge sources that can be added](#types-of-knowledge-sources-that-can-be-added)
- [Note on security](#-note-on-security)
- [Improving your agent's responses in Copilot Studio](#improving-your-agents-responses-in-copilot-studio)
- [Lab 06: Create a custom agent in with Copilot](#-lab-06-create-a-custom-agent-in-copilot-studio)
  - [Use case](#-use-case)
  - [Prerequisites](#-prerequisites)
  - [6.1 Use natural language to create an agent with Copilot](#61-use-natural-language-to-create-an-agent-with-copilot)
  - [6.2 Add an internal knowledge source using a SharePoint site - for Microsoft 365 licensed users with SharePoint included](#62-add-an-internal-knowledge-source-using-a-sharepoint-site---for-microsoft-365-licensed-users-with-sharepoint)
  - [6.3 Add an internal knowledge source by uploading a document - for non-Microsoft 365 licensed users who don't have SharePoint included](#63-add-an-internal-knowledge-source-by-uploading-a-document---for-non-microsoft-365-licensed-users-who-dont-have-sharepoint-included)
  - [6.4 Test agent](#64-test-agent)
- [Mission Complete](#-mission-complete)
- [Tactical Resources](#-tactical-resources)

## 🤔 What is a _custom_ agent?

A custom agent is a chatbot or virtual assistant that you create and design in Copilot Studio to help users with specific tasks or questions. It's called custom because:

- **You decide the purpose** - help users request vacation time, check order status, provide assistance with IT related questions.
- **You define the conversation** - what the agent says and how it should respond.
- **You ground it with your own data**  - connect to your enterprise data through the built-in supported knowledge resources.
- **You connect it to your own systems or applications** -  choose from connectors, flows, REST APIs and model context protocol servers.

> Think of it this way: you are building your own digital helper that can talk to users and complete tasks for them such as answering questions, collecting information required by a process, or connecting to your enterprise data.

### 🤖 What can a custom agent do?

A custom agent can fulfill the following:

- Ask users for information such as names, dates, or preferences.
- Save that information to a database or table.
- Look up data based on the questions asked and answer them.
- Work autonomously without users directly interacting with the agent.
- Trigger actions either on-demand through direct user interaction or autonomously such as sending emails or creating records.

### 👩🏻‍💻  Why use a custom agent?

- Saves time by automating repetitive tasks.
- Gives users a friendly, guided experience.
- Tailor it to your business or project needs.

### ✨ Example

You build a custom agent that helps employees request vacation leave.

It asks for their name, vacation dates, and their manager’s name, then saves the information into the designated system that managed vacation requests, such as a SharePoint list.

Now, instead of navigating to the SharePoint list and creating a new item, employees simply chat with the agent instead.

## 🗣️ Use natural language to create agents

Previously you learnt how to quickly build agents in Copilot Studio using prebuilt agent templates in [Lesson 05 - Get started quickly with pre-built agents](https://github.com/microsoft/copilot-studio-for-beginners/blob/main/05-using-prebuilt-agents/README.md). In this lesson, we'll dive into the conversational creation experience with Copilot. Copilot Studio makes it easy to build agents by chatting with Copilot, just like having a conversation.

In Copilot Studio, you don’t need to write code to create an agent. Instead, you describe what you want your agent to do in plain language, and Copilot helps you build it step by step through a chat-like experience.

## 🌱 But I'm new to "describing what I want" - what do I do?

Describing in natural language to create a custom agent might be a new concept for you. Whenever you use Copilot across Microsoft products and services, you are using natural language in the form of a _prompt_.

A prompt is the message or instruction you give to an AI agent to tell it what you want it to do. Think of it as giving directions to an assistant. The clearer your instructions are, the easier it is for your assistant to understand and act on them.

### 🪄 Why Prompts matter

- They guide the agent’s behavior.
- They help the agent understand what kind of conversation to have.
- A good prompt makes the agent more helpful and accurate.

### 📝 Tips for writing a good prompt

- Be clear and specific - say exactly what you want the agent to do.
- Think like the user - what will the user say? What should the agent reply?
- Include examples - if possible, give a sample interaction.

### ✨ Example

Let's say the HR team needs an agent to help with vacaction requests.

The prompt could be,

    “I want to build an agent that helps users submit a vacation request. When a user says they want to request time off, the agent should ask for their name, the start date of their vacation, the end date of their vacation, and their manager’s name. Once the user provides this information, the agent should save it to a SharePoint list called ‘Vacation Requests’ and post a notification in a dedicated Microsoft Teams channel.”

Why this prompt works:

- **Clearly states the goal** - submit a vacation request
- **Describes the user interaction** - what the user says and what the agent should ask
- **Lists the required data** - name, start date, end date, manager
- **Mentions where the data goes** - a SharePoint list called Vacation Requests

## 🔮 OK, I've created my agent... how do I next ground it with knowledge?

In Copilot Studio, knowledge sources are places where your agent can find information to give better answers. When you add these sources, your agent can pull in your enterprise data from places like Power Platform, Dynamics 365, websites, and other systems or services your company uses.

These sources work together with AI to help your agent respond more accurately to user questions, this is achieved through what is known as **generative orchestration**.

### 🌿 What is generative orchestration in the context of agents?

Generative orchestration means the agent uses AI to dynamically decide how to answer a question by combining its built-in language skills with information from your added knowledge sources.

When a user asks a question, the agent:

- Understands the question using AI.
- Can ask users for missing information by generating questions on the fly.
- Selects the most relevant knowledge sources.
- Searches those sources for answers.
- Generates a natural, helpful response using the information it found.

### 🏦 Why knowledge sources matter?

1. **Smarter answers** - when you add knowledge sources, your agent can give better, more accurate answers using real data from your organization.

1. **Less manual work** - you don’t have to write every possible response. The agent can search through your added sources and respond automatically.

1. **Use trusted information** - your agent can pull answers from systems you already use such as Dataverse, SharePoint, or company websites so that users have reliable information from a source of truth.

1. **Works with generative AI** - knowledge sources and AI help your agent understand questions and respond naturally, even if the question wasn't pre-programmed or added as a starter prompt.

1. **Flexible and expandable** - you can add knowledge sources anytime during set up or at later point in time, your agent grows smarter as your needs change.

### ✨ Example

Imagine you build an agent to help employees with HR questions. You add your company’s HR policy document and SharePoint site as knowledge sources.

When an employee asks, _“How many vacation days am I entitled to?”_, the agent uses generative orchestration to search those sources and reply with the correct policy without you having to write that answer manually. This saves you time in having to account for every possible question an employee may ask regarding their entitlements.

## Types of knowledge sources that can be added

1. **Public websites**
    - **What it does:** Searches specific websites (like your company’s site) using Bing.
    - **Why it’s useful:** Great for pulling in public-facing info like FAQs or product details.

1. **Documents**
    - **What it does:** Uses documents that you upload directly to your agent, such as PDFs or Word files. These uploaded files are stored securely in Dataverse.
    - **Why it's useful:** Enables your agent to answer questions based on internal guides, manuals or policies.

1. **SharePoint**
    - **What it does:** Connects to SharePoint folders or files using Microsoft Graph Search.
    - **Why it's useful:** Ideal for accessing team documents, HR policies, or project files stored in SharePoint.

1. **Dataverse**
    - **What it does:** Uses structured data from your Dataverse environment tables and rows, and can apply synonyms and glossary definitions for tables and columns for improving agent responses.
    - **Why it's useful:** When you need to look up enterprise data stored in Dataverse such as customer information.

1. **Real-time knowledge with connectors**
    - **What it does:** Lets your agent access live data from other enterprise systems such as Salesforce, ServiceNow, Dynamics 365, AzureSQL, Databricks, and more during a conversation, using the user's own permissions.
    - **Why it's useful:** It provides up to date, secure, and accurate responses without storing or duplicating data, making your agent smarter and safer.

1. **Azure AI Search**
    - **What it does:** Allows your agent to search through large sets of documents stored in Azure using semantic and vector search to understand user questions.
    - **Why it's useful:** Delivers accurate, trustworthy answers from complex data sources, supports citations, and scales well for large document collections with secure access controls.

## 🔒 Note on security

**Knowledge source authentication**

Some sources such as SharePoint and Dataverse require user authentication. This means the agent will only reference data in its response that the user is allowed to see. Whereas other sources may have additional configuration required for the agent to connect to it such as Azure AI Search which requires an Azure account and specifying an authentication type.

## Improving your agent's responses in Copilot Studio

After your agent is provisoned from the conversational creation experience, you'll want to test your agent against the instructions Copilot generated from your prompt. Improving your agent’s responses in Copilot Studio is all about making sure it understands your goals clearly and has the right information to work with.

1. **Refine the agent instructions** - this is where you tell your agent how it should behave. Use clear, specific language.

    For example:

    ✅ “Act like a friendly customer support agent who explains things simply.”

    ❌ “Be helpful.” (Too vague)

1. **Check the tone and language** - make sure the agent’s tone matches your audience.

    You can set it to be:

    - Friendly and casual.
    - Professional and concise.
    - Supportive and patient.

1. **Add or update knowledge sources** - if your agent needs to answer questions about a topic, make sure it has access to the right information.

    - Add links to websites, documents, or FAQs.
    - Keep the content up to date.
    - Use clear, well-structured information.

1. **Use Topics and Triggers** - If your agent needs to handle specific tasks or conversations, you can create topics with trigger phrases. This helps guide the conversation more precisely. We'll learn more about this in the following lesson.

1. **Test with real questions** - try asking your agent the kinds of questions users might ask.

    If the answers aren’t great:

    - Adjust the system instructions.
    - Add more examples or knowledge.
    - Rephrase your questions to see how it responds.

1. **Review and iterate** - improving an agent is an ongoing process!

    After publishing:

    - Collect feedback from users.
    - Watch for common questions or confusion.
    - Keep refining the agent’s setup.

## 🧪 Lab 06: Create a custom agent in Copilot Studio

We're now going to learn how to create a custom agent that can chat over your data

- [6.1 Use natural language to create an agent with Copilot](#61-use-natural-language-to-create-an-agent-with-copilot)
- [6.2 Add an internal knowledge source using a SharePoint site - for Microsoft 365 licensed users with SharePoint included](#62-add-an-internal-knowledge-source-using-a-sharepoint-site---for-microsoft-365-licensed-users-with-sharepoint)
- [6.3 Add an internal knowledge source by uploading a document - for non-Microsoft 365 licensed users who don't have SharePoint included](#63-add-an-internal-knowledge-source-by-uploading-a-document---for-non-microsoft-365-licensed-users-who-dont-have-sharepoint-included)
- [6.4 Test agent](#64-test-agent)

### ✨ Use case

We'll use the same use case from [Lesson 03 - Create a declarative agent for Microsoft 365 Copilot](https://github.com/microsoft/copilot-studio-for-beginners/blob/main/03-create-a-declarative-agent-for-M365Copilot/README.md#-use-case-scenario)

**As an** employee

**I want to** get quick and accurate help from the IT helpdesk agent for issues like device problems, network troubleshooting, printer setup

**So that I can** stay productive and resolve technical issues without delays

Let's begin!

### ✨ Prerequisites

1. **SharePoint site**

    We'll be using the **Contoso IT** SharePoint site from [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](/00-course-setup/README.md/#step-3-create-new-sharepoint-site).

    If you have not set up the **Contoso IT** SharePoint site, please head back to [Lesson 00 - Course Setup - Step 3: Create new SharePoint site](/00-course-setup/README.md/#step-3-create-new-sharepoint-site).

1. **Solution**

   We'll be using the **Contoso Helpdesk Agent** solution from [Lesson 04 - Creating a Solution for your agent](/04-creating-a-solution/README.md/#41-create-a-solution-publisher).

    If you have not set up the **Contoso Agent** solution, please head back to [Lesson 04 - Creating a Solution for your agent](/04-creating-a-solution/README.md/#41-create-a-solution-publisher).

### 6.1 Use natural language to create an agent with Copilot

1. Navigate to the Home page of Copilot Studio and in the field, enter the following prompt which describes the IT help desk agent. The prompt includes the goal of the agent, the context, the expected tasks and format of the agent's response.

   ```
   You are an IT help desk agent. Your goal is to assist users with their IT issues. You can access information from our company's knowledge base at https://support.microsoft.com/en-us. Your responses should be polite and helpful. If a user reports a slow computer, ask about the age of the device, current software versions, and if they've recently installed any new programs. If a user is experiencing trouble logging into their email, guide them through password reset procedures. You should be concise and informative, using step-by-step instructions with bullet points when appropriate.
   ```

   ![Enter prompt](assets/6.1_01_Prompt.png)

1. The conversational creation experience with Copilot will next load. You'll see Copilot is in progress of responding to you. The agent pane on the right will update shortly with details and instructions based on the prompt entered.

    ![Copilot conversational creation experience](assets/6.1_02_CopilotConversationCreationExperience.png)

1. Copilot will update the agent pane with a name, description and instructions based on the prompt entered. Cool right?!

   ![Agent pane displays name, description and instructions](assets/6.1_03_AgentInstructions.png)

1. Next, we'll ask Copilot to name our agent as,

    ```
    Contoso Helpdesk Agent
    ```

   ![Rename the agent](assets/6.1_04_NameAgent.png)

1. Copilot performs the request and we'll see that the name of the agent has been updated in the agent pane. Copilot next asks us to refine the instructions. It's asking how we should respond to particular issues and we'll request that it acknowledges the issue and format the response as bullet points. Copy and paste the following, and submit the request to Copilot.

    ```
    Acknowledge the issue with empathy and provide steps or troubleshooting as bullet points.
    ```

   ![Refine agent instructions](assets/6.1_05_RefineInstructions.png)

1. The instructions of the agent will be updated after Copilot has received the request. Next, Copilot is asking for public websites to ground the agent's knowledge. Enter the following and submit,

    ```
    https://support.microsoft.com
    ```

   ![Add publicly accessible website](assets/6.1_06_PublicWebsite.png)

1. The public website will be added as a knowledge source. If you don't see it in the agent pane, try scrolling down the pane and it'll appear as a knowledge source.

    Lastly, we're going to request that our agent does not answer HR related questions. This lets our agent know that it should not answer HR related questions asked by users. Enter the following and submit,

    ```
    Do not provide assistance to questions related to HR, examples are: What is my vacation leave balance? How many sick days do I have? What's the URL to our payroll portal? 
    ```

   ![Do not answer HR related requestions](assets/6.1_07_DoNotTalkAbout.png)

1. The instructions will be updated to not provide assistance with questions related to HR. Copilot is asking again if we'd like to request more modifications. We don't need to make further updates, enter the following and submit,

    ```
    No more modifications
    ```

   ![No more modifications](assets/6.1_08_NoMoreModifications.png)

1. Copilot confirms the agent is ready to be created. Before we create our agent, let's do a couple of things.

    For websites, you need to confirm which website(s) your organization owns that Bing will search through Copilot Studio.

    For learning purposes, we'll tick the checkbox that confirms ownership of the knowledge source. In reality, this would be _your company website_ that you have ownership of.

   ![Confirm website ownership](assets/6.1_09_ConfirmOwnershipOfKnowledgeSource.png)

1. Next we'll double check the solution that our agent will be created in, is the solution we created and selected as the preferred solution in [Lesson 04 - Create a new solution](https://github.com/microsoft/copilot-studio-for-beginners/blob/main/04-creating-a-solution/README.md#42-create-a-new-solution).

    Select the **ellipsis icon (...)** and select **Edit Advanced Settings**.

   ![Edit Advanced Settings](assets/6.1_10_EditAdvancedSettings.png)

1. The **Advanced Settings** modal will appear and we can see our solution created from earlier is selected by default. This is due to selecting our solution as the preferred solution in [Lesson 04 - Create a new solution](https://github.com/microsoft/copilot-studio-for-beginners/blob/main/04-creating-a-solution/README.md#42-create-a-new-solution).

    Select **Cancel.**

   ![View of Advanced Settings](assets/6.1_11_Solution.png)

1. Let's now create our custom agent! Select **Create**.

   ![Select Create](assets/6.1_12_CreateAgent.png)

1. Copilot Studio will begin provisioning our agent.

   ![Setting up agent](assets/6.1_13_SettingUpAgent.png)

1. Once our agent has been provisioned, we can see the details of the agent reflect what we requested during our Copilot conversational creation experience.

   ![Agent provisioned](assets/6.1_14_AgentCreated.png)

1. Scroll down and we'll see our instructions and the public website as the knowledge source for the agent.

   ![Instructions and knowledge sources](assets/6.1_15_InstructionsAndKnowledgeSources.png)

1. Let's now test our newly created agent. Enter the following question in the **Test** pane.

    ```
    How can I check the warranty status of my Surface?
    ```

   ![Test newly created agent](assets/6.1_16_TestNewlyCreatedAgent.png)

1. The Activity map will then load which shows us in real-time what path the agent is processing. In this scenario, our agent has understood the question and searches the knowledge sources. Currently we have one source which is the public website we added earlier using Copilot, which is what the agent is reviewing.

   ![Reviewing knowledge sources](assets/6.1_17_ReviewingKnowledgeSources.png)

1. Our agent then responds with answers that are outlined as bullet points, as defined in the instructions. The response has references to the web pages that the agent formed its response from. This enables users to verify the source of the answer. If you click on the reference, you'll be directed to the web page where you can review the source of the answer.

   ![References in response](assets/6.1_18_References.png)

1. You can also review the response and its sources by scrolling down the **Knowledge modal** in the Activity map.

   ![Referenced sources](assets/6.1_19_ReferencedSources.png)

Congratulations! You've built your first custom agent with Copilot in Copilot Studio 🙌🏻

### 6.2 Add an internal knowledge source using a SharePoint site - for Microsoft 365 licensed users with SharePoint

Previously with Copilot, we added a public website as an external knowledge source for our agent during the conversational creation experience. We're now going to add an internal knowledge source using a SharePoint site. This will be the SharePoint site you created during [Lesson 00 - Course Setup](/00-course-setup/README.md/#step-3-create-new-sharepoint-site).

> [!NOTE]  
> This exercise is valid for Microsoft 365 licensed users with SharePoint. If you don't have SharePoint in your Microsoft 365 license, skip to the [6.3 Add an internal knowledge source by uploading a document](#63-add-an-internal-knowledge-source-by-uploading-a-document---for-non-microsoft-365-licensed-users-who-dont-have-sharepoint-included) lab exercise.

1. Select **+ Add knowledge**.

   ![Select Add knowledge](assets/6.2_01_AddKnowledge.png)

1. Select **SharePoint**.

   ![Select SharePoint](assets/6.2_02_SelectSharePoint.png)

1. Paste in the **address of the SharePoint site** created in [Lesson 00 - Course Setup](/00-course-setup/README.md/#step-3-create-new-sharepoint-site) in the SharePoint URL field and select **Add**.

   ![Enter SharePoint site URL](assets/6.2_03_SharePointURL.png)

1. Update the **name** of the SharePoint site to `Contoso IT` and select **Add**.

   ![Update SharePoint site name](assets/6.2_04_UpdateSharePointSiteName.png)

1. The SharePoint site has now been added as a knowledge source with a status of _Ready_. The Status column will show whether the knowledge source has been loaded/connected to successfully, or if there is an issue.

   ![SharePoint site added](assets/6.2_05_SharePointSiteAdded.png)

### 6.3 Add an internal knowledge source by uploading a document - for non-Microsoft 365 licensed users who don't have SharePoint included

We'll now add another internal knowledge source by uploading a document directly to our agent. 

1. Select **Add knowledge**.

   ![Select Add knowledge](assets/6.3_01_SelectAddKnowledge.png)

1. Select **Upload file**.

   ![Select upload files](assets/6.3_02_SelectUploadFile.png)

1. Download this [sample file](https://github.com/microsoft/copilot-studio-for-beginners/blob/main/06-create-agent-from-conversation/assets/Contoso_Guest_WiFi_Connection_Guide.docx "download") and select it in your File Explorer. Select **Open**.

   ![Select document](assets/6.3_03_SelectDocument.png)

1. The file has been selected for upload. Select **Add** next.

   ![Select Add](assets/6.3_04_AddDocument.png)

1. The document will be in the process of being added to the agent. Wait until the upload has completed, do not close the browser window.

   ![Select Add knowledge](assets/6.3_05_UploadingDocument.png)

1. The status of the document will initially show as _In progress_, wait until the status has been updated to **Ready** before testing your agent.

   ![Select Add knowledge](assets/6.3_06_DocumentStatusReady.png)

Let's now test our agent!

### 6.4 Test agent

We'll test our three knowledge sources by asking questions to our Contoso Helpdesk Agent.

1. Select the **refresh** icon in the test pane.

   ![Refresh icon](assets/6.4_01_RefreshTestPane.png)

1. Enter the following question to test our public website (external) knowledge source.

    ```
   How can I find the serial number on my Surface device?
    ```

   ![Enter prompt to test website knowledge source](assets/6.4_02_TestWebsiteKnowledgeSource.png)

1. You'll next see the agent reviewing the knowledge sources and providing a response using the website knowledge source. There will be a reference to the web page it formed its answer from.

   ![Web page referenced in response](assets/6.4_04_WebPageReferenced.png)

1. If you scroll down the knowledge modal in the activity map, you'll see the other knowledge sources the agent searched, which is the SharePoint site and the uploaded file. However these were not used as in the **Referenced sources** section, the website knowledge source was referenced. The answer was grounded using the website knowledge source. If you select the reference, you'll be directed to the web page.

   ![Knowledge sources referenced and searched](assets/6.4_05_KnowledgeSourcesSearched.png)

1. Let's now test both our SharePoint site knowledge source and document knowledge source in a single message. Enter the following question.

   ```
   How do I access the Contoso VPN? How do guests connect to the Contoso Guest wifi?
   ```

   ![Test SharePoint and document knowledge sources](assets/6.4_06_TestSharePointAndDocumentKnowledgeSources.png)

> [!NOTE]  
> If you don't have SharePoint in your Microsoft 365 license, only enter the second question to test the document knowledge source.

6. Once again you'll see the agent reviewing the three knowledge sources to generate a response to the questions our single message.

   ![Reviewing knowledge sources](assets/6.4_07_ReviewingKnowledgeSources.png)

7. The agent responds to both questions in a single message, and separately references the SharePoint page and document of where it generated its response from. In the knowledge modal in the activity map, you'll see the SharePoint site and document used as the reference sources. You have full visibility of what knowledge sources were used to answer both questions.

   ![Knowledge sources referenced](assets/6.4_08_KnowledgeSourcesReferenced.png)

8. It's always good to verify the generated response is correct. Select the SharePoint site reference and the FAQs SharePoint page will load where you can scroll down to review the VPN instructions.

   ![Review SharePoint page](assets/6.4_09_VerifySharePoint.png)

9. Next, select the document reference and a modal will appear with the text from the document that reflects the answer.

   ![Review document](assets/6.4_10_VerifyDocument.png)

The agent can answer multiple questions in a single message, and search the knowledge sources + reference the knowledge sources in its response. Make sure to always verify the response is correct by reviewing the references.

## ✅ Mission Complete

Congratulations! 👏🏻 You've learnt how to use natural language to create your own custom agent that can chat over your data from three different knowledge sources 🙌🏻

This is the end of **Lab 06 - Create an agent with Copilot**, select the link below to move to the next lesson. Your custom agent created in this lab will be used in the next lesson's lab.

⏭️ [Move to **Add a new Topic with trigger** lesson](/07-add-new-topic-with-trigger/README.md)

Welcome to the elite. You now know how to forge digital agents that speak your language, reference your data, and support your team. Keep going—your mission’s just getting started.

## 📚 Tactical Resources

🔗 [Quickstart: Create and deploy an agent](https://learn.microsoft.com/microsoft-copilot-studio/fundamentals-get-started?context=%2Fmicrosoft-365-copilot%2Fextensibility%2Fcontext/?WT.mc_id=power-172617-ebenitez)

🔗 [Create and delete agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-first-bot?WT.mc_id=power-172617-ebenitez)

🔗 [Key concepts - Authoring agents](https://learn.microsoft.com/microsoft-copilot-studio/authoring-fundamentals/?WT.mc_id=power-172617-ebenitez)

📺 [Create a custom agent using natural language](aka.ms/ai-in-action/copilot-studio/ep1)

📺 [Add knowledge to your agents](https://aka.ms/ai-in-action/copilot-studio/ep2)

![mcs-agent-academy-recruit-06](https://m365-visitor-stats.azurewebsites.net/?resource=https://github.com/microsoft/mcs-agent-academy-recruit/tree/main/06-create-agent-from-conversation)
