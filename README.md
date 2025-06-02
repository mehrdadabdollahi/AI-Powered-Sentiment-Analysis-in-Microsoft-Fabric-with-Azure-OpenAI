
AI-Powered Sentiment Analysis in Microsoft Fabric with Azure OpenAI

In today's data-driven world, understanding customer sentiment at scale is a powerful asset for any organization. With the recent advancements in AI and the flexibility of Microsoft Fabric, we now have the tools to build intelligent, end-to-end solutions entirely within the Microsoft ecosystem.

In this post, I’ll walk you through a practical use case: performing sentiment analysis on customer feedback using Microsoft Fabric, Azure OpenAI, and PySpark—all orchestrated with Fabric Data Pipelines and visualized in Power BI.

What We’re Solving

Many organizations collect large volumes of textual feedback from customers but lack the tooling or bandwidth to manually interpret and categorize this information. By using Azure OpenAI's large language models, we can automate this process—classifying feedback as Positive, Neutral, or Negative with minimal setup.


Solution Overview

The project breaks down into several key steps:

1. Create a Microsoft Fabric Workspace and Lakehouse

Start by setting up your Fabric workspace and creating a Lakehouse where you'll store the customer feedback CSV file. This serves as the central data source for the entire workflow.

2. Prepare the Customer Feedback Data

We use a sample CSV file containing 100+ rows of raw customer feedback. This file is uploaded into a table in the Lakehouse using the built-in dataflow or file upload features.

3. Deploy Azure OpenAI Model in Azure AI Studio

Head over to Azure AI Studio (formerly Azure AI Foundry), create a new deployment using the gpt-35-turbo model (or gpt-4 if needed), and retrieve your endpoint URL and key. This model will be used to perform the actual sentiment classification via REST API.

4. Write and Execute PySpark Code in a Fabric Notebook

Within your Fabric workspace, create a new notebook using PySpark. The notebook reads the feedback data, sends it to the Azure OpenAI endpoint, and appends the resulting sentiment back into a new table in the Lakehouse.

5. Orchestrate with a Data Pipeline

To automate the process, add the notebook to a Data Pipeline and schedule it. This allows the solution to run at regular intervals, for example, whenever new feedback data arrives.

6. Visualize with Power BI

Finally, connect Power BI directly to the Lakehouse and build a report that visualizes sentiment distribution, trends over time, and highlights positive/negative feedback.


Demo and Resources

I’ve created a complete walkthrough in a 10-minute video on my YouTube channel, where I cover each step with a live demo.
👉 Watch it here: https://www.youtube.com/watch?v=S7X7y2qBraQ 
📁 Get the code and sample dataset: https://github.com/mehrdadabdollahi/AI-Powered-Sentiment-Analysis-in-Microsoft-Fabric-with-Azure-OpenAI 


Why This Matters

This solution demonstrates how easily AI can be integrated into enterprise-scale data pipelines with Microsoft Fabric. Without needing to manage infrastructure or write complex ML models, you can now deliver business-critical insights quickly and reliably.

Whether you're a data engineer, developer, or analytics professional, this approach can be adapted to many use cases—product reviews, support tickets, survey results, and more.

I’d love to hear how you might apply this in your own work or how you'd extend it. Feel free to reach out or drop your ideas in the comments section of the video.

