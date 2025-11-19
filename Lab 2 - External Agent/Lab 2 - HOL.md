## Create a watsonx.ai Agent

We will create a Comparison Agent in watsonx.ai's Agent Lab as part of this setup:

From the Home page of watsonx.ai, click on Build an AI agent to automate tasks

<img width="1512" height="797" alt="image" src="https://github.com/user-attachments/assets/149fcee5-7541-48c4-9f01-5c6ac5e964ec" />


Let's start the **Comparison Agent**. 

### Comparison Agent  
#### Setup  
1. **Name**: `Comparison Agent`
2. **Description**: 
   ```
   The agent compares the given data with additional information gathered from Google search results.
   ```
<img width="3440" height="1984" alt="image" src="https://github.com/user-attachments/assets/348d20d8-baf6-4a9a-b21b-8b41c026d409" />

#### Configuration    
1. Choose **LangGraph** as the framework.  
2. Select **ReAct** as the architecture. 
3. Enter the following for **Instructions**. These instructions guide your agent on what tasks it should perform:
   ```
   You are an expert of automobile industry combining given details present in your context window.  Your task is crawl and search the Top 3 product URLs (strictly from the automobile industry) and to analyse and compare products on the following features strictly: Range, Pricing, Acceleration, Top Speed, Interior and Safety Features If a feature is not applicable, mark it as N/A. Additionally, perform a SWOT analysis of top products (Strengths, Weaknesses, Opportunities, and Threats) Present the comparison in 3 tables one for the comparison , second for the rating numerical rating (X/5) and a star rating (★ out of ★★★★★) for each feature  and  third for the SWOT analysis. Give heading to each table . After every table give two divider.
   Instructions:
   1. When asked for competitors of the given product, make sure that you provide only the name of the products and URLs of the products below the corresponding name.
   2. The generated product URLs must be strictly from the automobile industry.
   3. Title for Table 1: Feature Comparison
   4. Title for Table 2: Rating Comparison
   5. Make sure that the Rating Comparison table has both the numerical(X/5) and star rating(★ out of ★★★★★)
   6. The products should be the column names in all the tables.
   7. The font of the Table Title must be bold and the font size must be 40% bigger as compared to the rest of the text.
   8. Add appropriate space between each section in the table.
   9. Name the References as Competitors
   ```

   <img width="3442" height="1956" alt="image" src="https://github.com/user-attachments/assets/89ef921b-1abb-4660-99d8-031decc4b94d" />

   > **Note:** The Google Search Tool is added by default to the Agent. However, if you accidentally click the delete icon, follow the Tool steps below. Otherwise, you can skip this.

#### Tools  
1. Click on the **Add Tool**.
  <img width="1675" height="831" alt="image" src="https://github.com/user-attachments/assets/7b37dbe7-6bf9-4bcc-bcfa-84b7055cfa4a" />

2. Select **Google Search** as the tool to gather data.  
  <img width="3190" height="1735" alt="image" src="https://github.com/user-attachments/assets/551ffd84-7ec6-4aa3-9bef-91e9392c88fb" />

#### Saving and Deploying
Once the agent is created, save and deploy:
1. Click on the Disk icon (marked as 1), then to **Save As**
  <img width="3442" height="1956" alt="image" src="https://github.com/user-attachments/assets/4dc081f9-f3a1-481b-9f63-fceb23c3c845" />

2. Select **Agent** and click **Save**
  <img width="3434" height="1988" alt="image" src="https://github.com/user-attachments/assets/0d31b2fd-ef1f-4d2e-ad0d-86f52a4649f0" />

3. Click on the **Deploy** button
4. On the **Deploy as an AI service** page, you will be prompted to create a user api key. This will be used by **watsonx** to deploy your agent and is different from the **Cloud API key** created earlier. Click on **Create**. 
  <img width="3454" height="492" alt="image" src="https://github.com/user-attachments/assets/b2eaeefc-3c5e-45c5-bb40-2eec637b31c1" />

5. You'll be directed to another webpage. Click on **Create a key**.
  <img width="3414" height="1138" alt="image" src="https://github.com/user-attachments/assets/b7cc44cd-5df2-450b-8e32-8207077977e3" />

6. Once a key is created, navigate back to **Deploy as an AI service** page. Click on **Reload**.
  <img width="3379" height="488" alt="image" src="https://github.com/user-attachments/assets/f3cd10f5-ffca-405c-876e-1628ea5df0e5" />

7. Make sure your **Targeted deployment space** (created previously when **watsonx** project was created) has been selected (marked as 1), click **Deploy** to deploy the agent (marked as 2)
  <img width="1512" height="795" alt="image" src="https://github.com/user-attachments/assets/c0df4734-e7df-4c72-8106-26b48ec0bf4a" />

To deploy your agent on Orchestrate, follow the steps below: 

1. Go to the homepage of watsonx.ai Agent Lab.
  <img width="1512" height="796" alt="image" src="https://github.com/user-attachments/assets/4df91223-07f9-4a0b-8ea3-05a9c1ebf5b5" />

2. Click on the hamburger menu and select **Deployments**.  
  <img width="1512" height="836" alt="image" src="https://github.com/user-attachments/assets/83fbbc71-00f7-4402-910d-f18559a702ee" />

3. Click on the **Spaces** tab and select the space where you deployed the agent.  
  <img width="1512" height="795" alt="image" src="https://github.com/user-attachments/assets/2aeb5f35-8180-43ec-98b1-6d4f0449f17d" />

4. Click on the **Assets** tab and select the agent.  
  <img width="1512" height="794" alt="image" src="https://github.com/user-attachments/assets/1c97ea2d-e3ba-4b16-8c58-893b26e54f81" />

5. Then you will go the the main deployment page select your agent from the list.
  <img width="1512" height="793" alt="image" src="https://github.com/user-attachments/assets/16c92db9-06f3-43e5-88ad-95a58a9c5070" />

6. Then copy the streaming **Public endpoint**.
  <img width="1512" height="795" alt="image" src="https://github.com/user-attachments/assets/77250f17-b15f-4c60-8181-8ebaa4d80a91" />

Now let's go to Orchestrate, create other agent and import this agent in that one.

> **YOU DID IT! you just created and deployed your first AI Agent.**
> Now let's build more agents and integrate them together.

## Integrating watsonx.ai agent as an External Agent in watsonx Orchestrate

1. Scroll down to the Toolset section, then in the Agents section click on the Add Agent button.
  <img width="3448" height="1920" alt="image" src="https://github.com/user-attachments/assets/7cc7fd85-4257-4b13-9100-0e9ff1dfe06d" />

2. From the pop-up menu, select the Import.
  <img width="3448" height="1918" alt="image" src="https://github.com/user-attachments/assets/0f74e677-eb24-4b42-82fc-ade2b8c80587" />

> **Note:** : We are now adding the Comparison Agent (an external agent) to the Product Agent, enabling it to delegate tasks to them.

3. On the next page, ensure that External Agent is selected (see #1 on image below). If it’s not already selected, please choose it, then click the Next button (see #2 on image below).
   <img width="1729" height="958" alt="image" src="https://github.com/user-attachments/assets/d0eb4e9b-e88c-4cbb-ba44-a6c5d603166f" />

4. On the next page, enter the following information:
    1. **Provider**: From the drop down select **watsonx.ai**. 
       >NOTE: If this isn't set, you will encounter the following error: `Authentication request failed because the expected Bearer token is missing from the request header`
    2. **API key**: Enter your IBM Cloud API key.
    3. **Service instance URL**: Enter the public streaming endpoint URL of the agent that we copied in [step 6 above](#integrating-watsonxais-agent-as-an-external-agent-in-watsonx-orchestrate).
    4. **Display name**: `Comparison-Agent-v1`
    5. **Description of agent capabilities**: 
       ```
       This agent is designed to search for competitive URLs of input product and compare the given compare the given data with additional information gathered from Google search results. Its task is to carefully analyze the input data, extract key insights, and identify both differences and similarities. The findings should be presented in a well-structured table format, making it easy to understand and compare the information at a glance.
       ```
    6. Click on the **Import Agent** button.

    <img width="3452" height="1920" alt="image" src="https://github.com/user-attachments/assets/55a053f3-6f52-4a7c-aa2d-766419c9ac44" />


5. Once the delegated agents are added, they will appear as shown in the image below.
   <img width="3410" height="1724" alt="image" src="https://github.com/user-attachments/assets/9fd5efeb-6e6b-4dd0-96e0-25a4723c9b5a" />


6. Scroll down to the **Behavior** section, add the following for **Description**:

    ```
    This agent is responsible for handling product-related queries using Retrieval-Augmented Generation (RAG) on the product catalog.
    For general product queries, it retrieves structured information directly from the knowledge base.
    For queries involving URLs or web references or comparison, it delegates the task to the Comparison Agent.
    ```

    Click the **Deploy** button:
    <img width="3450" height="1918" alt="image" src="https://github.com/user-attachments/assets/9fdf9f3f-c344-4e18-8077-43ec8aefa9ee" />


> **Note:** : The Product Agent is now ready to handle product-related queries, delegating tasks to the **Comparison Agent** as needed.

## Experience Agents in Action
Follow the steps above, then try interacting with the use case using these sample queries:

1. Go to the hamburger menu and select **Chat**
   <img width="1612" height="828" alt="image" src="https://github.com/user-attachments/assets/9e50a565-624b-408a-b6cc-7b9007e023a1" />


2. Select the **Product Agent** from the dropdown menu, and you should be good to go.
   <img width="3456" height="1914" alt="image" src="https://github.com/user-attachments/assets/4796d533-6483-4066-9e9f-384e7f3e5c29" />


3. Product Agent

   Ask the following queries which should be routed to the Product Agent:
   ```
   What are the products of ABC Motors.
   ```
   ```
   Give me the info of Zenith X3.
   ```
   <img width="3364" height="1712" alt="image" src="https://github.com/user-attachments/assets/9dbc7ea2-c2d0-4b5b-af05-375617570505" />

 

3. Comparison Agent

   To compare the retrieved data, ask:
   ```
   Give me URLs of the competitors of the above product and show me the comparison as well.
   ```
   <img width="3434" height="1978" alt="image" src="https://github.com/user-attachments/assets/a2b0c6a7-cf4b-4974-80aa-d70d44a0b635" />

   <img width="3432" height="1972" alt="image" src="https://github.com/user-attachments/assets/5b3aca16-e33e-40bc-be01-a70e31460e1f" />


*Due to the randomness nature of Large Language Models, the output may not be exactly macth the output shown above*

