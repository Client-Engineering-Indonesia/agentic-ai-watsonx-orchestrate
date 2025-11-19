# Simple RAG - Chat with Documents

## Create an Orchestrate Agent

### Product Agent
1. Go to the Orchestrate home page, click on the hamburger menu (☰), select **Build**, and then choose **Agent Builder**.
   <img width="3414" height="1686" alt="image" src="https://github.com/user-attachments/assets/f2b7520f-175b-4581-bfa2-4f61500a9a84" />

2. Click on the **Create Agent** button.
   <img width="3424" height="1694" alt="image" src="https://github.com/user-attachments/assets/990f11ad-fe9f-4ca3-96b1-def69d1f7e94" />

3. Select **Create from scratch** (#1 on image below)
   
   **Name** (#2 on image below):
   ```
   Product Agent
   ```
   **Description** (#3 on image below):
        
   ```
   This agent is designed to search for a specified product and retrieve its details and features using Retrieval-Augmented Generation (RAG) on the product catalog. It presents the information in a clear and structured format, ensuring systematic organization of key product data, making it easy to understand and use.
   ```

   Click on **Create** button
   <img width="3424" height="1726" alt="image" src="https://github.com/user-attachments/assets/b1efd1aa-b2af-4e64-ada0-48158d0fee82" />

4. Once the agent is created, go to the **Agent Configuration** page and set the model to `llama-3-405b-instruct` and the Agent style to Default.
   <img width="3456" height="1924" alt="image" src="https://github.com/user-attachments/assets/e783258f-0d77-49f0-9414-b7da9ac91b6e" />

5. Scroll down to the **Knowledge** section and click on the **Choose knowledge** button.
   <img width="3446" height="1920" alt="image" src="https://github.com/user-attachments/assets/b1e54851-118e-4f64-9d8e-618b3568b8e4" />

6. After clicking the **Choose knowledge** button, a pop-up window will appear. Select **Upload Files**, then click **Next**.
   <img width="3454" height="1916" alt="image" src="https://github.com/user-attachments/assets/1b08457c-8ca9-4882-8caf-12f090843e6c" />

7. Next, choose the knowledge source. In our case, it's the Product Catalog. Drag and drop the file into the designated area.
   <img width="3450" height="1920" alt="image" src="https://github.com/user-attachments/assets/858bf28b-1b4e-484b-b201-034a1834ac7e" />

8. Once the file is uploaded, the screen will look like the one below. Click **Next** to proceed.
   <img width="3450" height="1922" alt="image" src="https://github.com/user-attachments/assets/4ccbf466-49da-45fa-a723-e79d2937ef18" />

9. Add the description below in the **Description** field, and then click **Save**.
   **Description:**
   ```
   Your knowledge base is the document that contains all the product-related information. All queries related to the product will be addressed using this document as the primary source.
   ```
   <img width="3454" height="1914" alt="image" src="https://github.com/user-attachments/assets/3e1c9eea-f6a0-4c25-8edd-4bf7ef012e6f" />

10. After completing all the above steps, your knowledge source will be added and will appear as shown in the image below.

   <img width="3454" height="1912" alt="image" src="https://github.com/user-attachments/assets/afe92666-d35c-4c04-83bd-680cf5dc2bce" />

12. Ask questions that included in the documents such as 
   ```
    What are the products of ABC Motors.
   ```
   <img width="1507" height="806" alt="image" src="https://github.com/user-attachments/assets/98410ec3-7fff-476d-a0fa-1df8874fef80" />






