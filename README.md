# n8n_Automation_Ai_News_Summarizer
This is workflow which triggers everyday exacactly at 10 am through shedule trigger Here Ai  which was published within 24 hour reads all the news related to AI and Machine learning  Surmmarizes it and sends top 2 news to groq model and than model summarizes these news and give me directly to my whatsapp 
# AI-Powered RSS News Summarization Agent

An automated [n8n](https://n8n.io/) workflow designed to fetch, filter, and intelligently summarize news from RSS feeds. By leveraging a multi-model AI Agent setup (powered by Google Gemini and Groq), this workflow extracts the most relevant information and delivers concise updates autonomously.

## 🚀 Features

* **Automated Data Ingestion:** Runs on a scheduled trigger to consistently pull the latest articles from targeted RSS feeds.
* **Smart Filtering & Rate Limiting:** Utilizes custom JavaScript and native n8n filtering to discard noise and limit the volume of data processed, saving AI token costs.
* **Advanced AI Agent:** Integrates Google Gemini and Groq models within an autonomous agent structure to analyze and summarize content.
* **Custom Output Delivery:** Automatically formats and sends the final AI-generated insights via messages.

## 🧩 Workflow Architecture

Here is a breakdown of the core nodes used in this workflow:

1. **Schedule Trigger:** Initiates the workflow at predefined intervals (e.g., hourly, daily).
2. **Code (JavaScript):** Custom logic to set up parameters or pre-process data before fetching feeds.
3. **RSS Read:** Ingests the XML/RSS feed data.
4. **Filter & Limit Nodes:** Sifts through the incoming feed to keep only relevant articles (based on keywords/dates) and restricts the batch size.
5. **AI Agent:** The core intelligence layer. Uses **Google Gemini** as the primary conversational model and **Groq** for rapid processing tasks, supported by short-term memory and tools.
6. **Send Message:** Dispatches the summarized insights to your preferred destination (e.g., Telegram, Slack, Discord, or Email).

## 📋 Prerequisites

To run this workflow, you will need:
* A running instance of **n8n** (Works great on self-hosted Docker setups).
* An API Key for **Google Gemini**.
* An API Key for **Groq**.
* (Optional) Credentials for your chosen messaging platform if you are sending the output to a specific app.

## 🛠️ Installation & Setup

1. **Download the Workflow:** Clone this repository or download the `agent_prac.json` file.
2. **Import into n8n:**
   * Open your n8n workspace.
   * Go to the top right of your canvas, click `...` > **Import from File**.
   * Select the downloaded JSON file.
3. **Configure Credentials:**
   * Open the **AI Agent** node and set up your Google Gemini and Groq API credentials.
   * Update the **RSS Read** node with your preferred RSS feed URL.
   * Configure the **Send Message** node with your destination credentials.
4. **Activate:** Toggle the workflow to **Active** (top right corner) so the Schedule Trigger can begin running.

## 🤝 Contributing

Feel free to fork this repository and submit pull requests if you have improvements, such as additional AI tools, alternative chunking methods, or new output destinations.

