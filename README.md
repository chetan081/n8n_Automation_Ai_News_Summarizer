# n8n_Automation_Ai_News_Summarizer
This is workflow which triggers everyday exacactly at 10 am through shedule trigger Here Ai  which was published within 24 hour reads all the news related to AI and Machine learning  Surmmarizes it and sends top 2 news to groq model and than model summarizes these news and give me directly to my whatsapp 

# AI-Powered RSS News Summarization Agent

An automated [n8n](https://n8n.io/) workflow designed to fetch, filter, and intelligently summarize AI news from top RSS feeds (like HuggingFace, TechCrunch, OpenAI, and Ollama). The workflow extracts the most relevant daily updates and delivers concise, friendly summaries directly to WhatsApp.

## 📱 The Final Output
Here is what the automated AI summary looks like when delivered to WhatsApp:

![WhatsApp Output](whatsapp-output.jpeg)<img width="738" height="1600" alt="WhatsApp Image 2026-05-20 at 17 08 19" src="https://github.com/user-attachments/assets/16bb9afe-80f7-4a6b-a7a2-4f5847197812" />


---

## 🚀 Features

* **Automated Data Ingestion:** Consistently pulls the latest articles from multiple targeted RSS feeds.
* **Time-Based Filtering:** Automatically filters out older news, keeping only articles published within the last 24 hours.
* **Cost & Volume Control:** Limits the batch size (e.g., top 2 articles) to prevent spam and save AI token costs.
* **Advanced AI Summarization:** Instructs the AI agent to summarize complex articles into three short, friendly sentences perfect for instant messaging, complete with source links.
* **Direct Messaging Delivery:** Automatically formats and sends the final AI-generated insights to WhatsApp.

---

## 🧩 Workflow Architecture & Node Setup

Here is a visual breakdown of how the workflow is constructed in n8n:

### 1. Fetching the Data (RSS Read)
The workflow starts by pulling raw XML feed data from designated AI news sources.
![RSS Read Node](rss-read.png)<img width="1386" height="887" alt="Rss_read" src="https://github.com/user-attachments/assets/0154f506-3ae0-4038-a271-5611b14aa36c" />


### 2. Time Filtering
A Filter node evaluates the `isoDate` of each article, discarding anything older than 24 hours so you only get fresh news.
![Filter Node](filter.png)<img width="1370" height="892" alt="Filter24hour" src="https://github.com/user-attachments/assets/28b231ef-cdd6-4f96-8326-c797378a41b7" />


### 3. Rate Limiting
To keep the updates digestible, a Limit node restricts the output to the top 2 items from the filtered list.
![Limit Node](limit.png)<img width="1367" height="877" alt="ratelimit" src="https://github.com/user-attachments/assets/cc2b824e-db1c-421c-a48c-ba1d5fc672dc" />


### 4. AI Agent Summarization
The core intelligence layer. The AI Agent is prompted to summarize the content into a friendly, three-sentence WhatsApp update, including the main takeaway and a link to the full story.
![AI Agent Node](ai-agent.png)<img width="1392" height="876" alt="ai_agent_summarization" src="https://github.com/user-attachments/assets/f1472309-3c99-4ca6-893e-3a20b63405bc" />


---

## 📋 Prerequisites

To run this workflow, you will need:
* A running instance of **n8n** (Cloud or Self-hosted).
* API credentials for your chosen AI Model (e.g., Google Gemini, Groq, or OpenAI) configured in n8n.
* Credentials for your WhatsApp Business API / Twilio (or your preferred messaging node) to send the final output.

## 🛠️ Installation & Setup

1. **Download the Workflow:** Clone this repository or download the `.json` workflow file.
2. **Import into n8n:**
   * Open your n8n workspace.
   * Go to the top right of your canvas, click `...` > **Import from File**.
   * Select the downloaded JSON file.
3. **Configure Credentials:**
   * Open the **AI Agent** node and connect your AI API credentials.
   * Ensure the **WhatsApp/Messaging** node is connected to your sending account.
4. **Activate:** Toggle the workflow to **Active** (top right corner) so it can run on its automated schedule.

## 🤝 Contributing

Feel free to fork this repository and submit pull requests if you have improvements, such as adding new RSS sources, integrating different AI models, or expanding to platforms like Telegram or Discord.

## 📝 License

This project is open-source and available under the [MIT License](LICENSE).
