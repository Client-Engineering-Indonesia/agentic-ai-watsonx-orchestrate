# Lab 3 - Adding Custom API 

## Financial Analyst Agent Creation

In this section, you will go through the process of creating an AI agent in watsonx Orchestrate:

1. To start building agents, you can click the Create new agent link as referenced in step 5 or alternatively, click the top left navigation menu, expand the Build section (annotated with red arrow) and select Agent Builder (annotated with red rectangle). This will redirect you to the Manage agents page.
   <img width="2252" height="1224" alt="image" src="https://github.com/user-attachments/assets/6010e62c-94a9-4545-808e-7ab505e70b40" />

2. The Manage agents page will initially be blank since no agents have been created yet. As you create more and more AI agents that can reason and act, the Manage agents page will be populated with those agents. Note the analytics captured at the top of the page including Total messages, Failed messages, and Latency average (annonated with red rectangle). Also, note the Discover button (annonated with red oval) which you can click to explore and discover the catalog of pre-built agents and tools in watsonx Orchestrate. Click Create agent button (annotated with red arrow) to start building your first agent.
   <img width="2028" height="1048" alt="image" src="https://github.com/user-attachments/assets/152c11e4-0ba9-410e-a080-de01408c7d5d" />

3. On the Create an agent page, select **Create from scratch** tile (annotated with red rectangle), provide a **Name** and a **Description** for the agent and click **Create** (annotated with red arrow).

Name: 
```
Financial Analyst Agent
```
Description: 
```
Agent skilled at financial research using internal knowledge and external search of public information.
```
The natural language description of an agent is important as it is leveraged by the agentic solution to route user messages to the right agent skilled in addressing the request. For more details, please review the [Understanding the description attribute for AI Agent](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-creating#understanding-the-description-attribute-for-ai-agent) documentation.

watsonx Orchestrate supports creating an agent from scratch or from a template which involves browsing a catalog of existing agents and using attributes of another agent as a template for the new agent. For this lab, you will be creating agents from scratch.
<img width="1874" height="1184" alt="image" src="https://github.com/user-attachments/assets/08448a35-2c51-43b5-9bb5-4e510649011b" />

### Agent Configuration with Knowledge Base
After the AI Agent is created, in this section, you will go through the process of configuring the agent with knowledge and tools to enable it to respond to queries using information from the knowledge base and perform tasks using the tools.

4. Next, you will go through the process of configuring your agent. The Financial Analyst Agent page is split in two halves. The right half is a **Preview** (annotated with red oval) chat interface that allows you to test the behavior of your agent. The left half of the page consits of five key sections (annotated with red rectangle) that you can use to configure your agent.

   - Profile: The **Profile** section consists of the description of the agent which you provided as part of creating the agent. You can always go to this section to edit and refine the description of the agent as needed. In this section, you also specify the **Agent style** whether *Default* or *ReAct*. 
   
   *Note: For more details, Please consult the [Choosing a reasoning style for your agent](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/base?topic=agents-choosing-reasoning-style-your-agent) documentation to understand the difference and how it affects the agent's behavior.*

   - Knowledge: The **Knowledge** section is where you can add knowledge to the agent. Adding knowledge to agents plays a crucial role in enhancing their conversational capabilities by providing them with the necessary information to generate accurate and contextually relevant responses for specific use cases. You can directly upload files to the agent, or connect to a Milvus or Elasticsearch instance as a content repository. Through this **Knowledge** interface, you can enable your AI agents to implement the Retrieval Augmented Generation (RAG) pattern which is a very popular AI pattern for grounding responses to a trusted source of data such as enterprise knowledge base.
   
   *Note: For more details, please consult the [Adding knowledge to agents](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-adding-knowledge) documentation.*

   - Toolset: While *Knowledge* is how you empower agents with a trusted knowledge base, then **Toolset** is how you enable agents to take action by providing them with *Tools* and *Agents*. Agents can accomplish tasks by using **Tools** or can delegate tasks to other **Agents** which are deeply skilled in such tasks.

   *Note: For more details, please consult the [Adding tools to an agent](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-adding-tools) and [Adding agents for orchestration](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-adding-orchestration) sections of the documentation.*
   
   - Behavior: The **Behavior** section of the agent configuration is where you provide instructions to the agent to define how it responds to user requests and situations. You can configure rules that dictate when and how the agent should take action. These rules help the agent behave in a predictable and consistent manner, delivering a seamless user experience.

   *Note: For more details, please consult the [Adding instructions to agents](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-adding-instructions) documentation.

   - Channels: The **Channels** section is how you expose your agent to different communication platforms (for example, Slack). This integration improves user experience and agent accessibility. At ths time of this lab writing, channel support is in *Preview* with support for *WebChat*, *Microsoft Teams*, and *WhatsApp with Twilio*. The product will be adding support for additional channels where you can deploy your agent(s).

   *Note: For more details, please consult the [Connecting to channels](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/base?topic=agents-connecting-channels) documentation.

5. On the agent configuration page, review the *Description* of the agent in the **Profile** section and keep as is (no edits necessary). Also, keep the *Agent style* selection as **Default**. Next, scroll down to the **Knowledge** section, or click the **Knowledge** shortcut (annotated with red oval). In the Knowledge section, add a description to inform the agent about the content of the knowledge. For this lab, add the following description as we will provide the agent with a number of recent earnings reports for a handful of companies.

Description: 
```
This knowledge addresses all details about earning reports for the companies of interest. Research analysts can ask about any details from earning reports.
```

Next, you have to choose how to provide knowledge information to the agent. watsonx Orchestrate supports adding knowledge to the agent either by uploading files directly through the UI or by pointing to a content repository (Mivlus or ElasticSearch). The [Adding knowledge to agents](https://www.ibm.com/docs/en/watsonx/watson-orchestrate/current?topic=agents-adding-knowledge) documentation provides more details. For this lab, click the **Upload files** button (annotated with red arrow) to upload pdf files capturing earnings reports for AMZN, META, NVDA, and NFLX.

<img width="2532" height="1438" alt="image" src="https://github.com/user-attachments/assets/de2eda68-b45f-4457-b98d-3ffd791d35e9" />



Drag and drop the following pdf files to upload to the knowledge for the agent :
   - [AMZN-Q4-2024-Earnings.pdf](assets/AMZN-Q4-2024-Earnings.pdf)
   - [META-Q4-2024-Earnings.pdf](assets/META-Q4-2024-Earnings.pdf)
   - [NFLX-Q4-2024-Earnings.pdf](assets/NFLX-Q4-2024-Earnings.pdf)
   - [NVDA-Q4-2024-Earnings.pdf](assets/NVDA-Q4-2024-Earnings.pdf)

<img width="2606" height="1448" alt="image" src="https://github.com/user-attachments/assets/1f811ceb-1f29-4dc5-9f9f-0f29961df9b7" />

6. Once the files are all uploaded to the knowledge base, you can start testing the agent to validate how it can respond to questions using this knowledge base. The uploaded files get processed and prepared to be leveraged by the agent. After the upload completes, test the agent by asking a few questions such as:

```
Can you tell me about Meta's business
```

You should see the responses being retrieved from the uploaded documents and then the final response generated by the agent as illustrated in the figure below. Click *Show Reasoning* (annotated with red oval) and also *Step 1* to review the agent's reasoning and validate it is correctly retrieving the answer from the knowledge base. Additionally, click the *Toggle Citation* icon (annotated with red arrow) to show the actual document from which the response is retrieved. Note it is correctly getting the response the Meta's earnings report (annotated with red rectangle).

<img width="2608" height="1454" alt="image" src="https://github.com/user-attachments/assets/c42067f0-a75d-4b71-aced-a22277ed05f0" />


Try another test as follows:

```
I'm interested in learning more about Meta and Amazon. Can you tell me a bit about their businesses?
```
Observe the response being generated using the knowledge base. As before, click the *Toggle Citation* icon (annotated with red arrow) to show the refernced documents. Click *Next* icon (annonated with red oval) to review all retrieved documents.

<img width="2610" height="1446" alt="image" src="https://github.com/user-attachments/assets/2845a76b-5222-4fb0-a68e-88389097d805" />


Feel free to try a test like ```Give Toyota q4 financial results``` and review the response from the agent which should indicate that it has no information about Toyota as shown in the figure below.

<img width="2602" height="1432" alt="image" src="https://github.com/user-attachments/assets/40ce2783-90f1-4579-8e9d-f9533e43a150" />


At this time, it is worthwhile taking a moment to reflect on what you've developed so far. You have designed an agent and empowered it with a knowledge base to enable it to respond to queries in context using its knowledge base. *Congratulations!!*

Reviewing the architecture, you've completed the part of the agentic solution which involved creating the Financial Analyst agent and empowering it with a knowledge base (annotated with red rectangles in the figure below). In the next section, you will work through the process of creating the **Financial API Agent** and the **Web Search Agent** which you will then add as collaborator agents to the **Financial Analyst Agent**.

<img width="1586" height="878" alt="image" src="https://github.com/user-attachments/assets/bbd31cb0-c245-42ae-b25f-2464a7f17cbb" />



