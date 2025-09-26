# 🎭 Market Event Sentiment Analysis Pipeline (n8n + Ollama)

This n8n workflow automates **high-volume sentiment analysis** on social media data related to major market/policy events, providing real-time sentiment distribution and statistical outputs.

---

## 🚀 Technical Workflow Overview (End-to-End Automation)

1. **Twitter Data Pulling**
    - Fetches relevant tweets from a social media API (`twitterapi.io`) using a targeted query related to the specific market event.
    - Supports pagination for high-volume data ingestion.

2. **Cleaning & Pre-processing**
    - Extracts essential data fields (ID, URL, Text, Username) and prepares the content for LLM processing.

3. **Sentiment Classification (AI Core)**
    - Uses a **self-contained LLM (Llama3 via Ollama + LangChain)** to classify each text as: `positive`, `negative`, or `neutral`.
    - **Achievement:** Demonstrates a **cost-effective, local AI architecture** suitable for private/high-volume data processing.

4. **Data Aggregation & Formatting**
    - Normalizes outputs and calculates key sentiment metrics: Total tweets, Positive %, Negative %, and Neutral %.

5. **Visualization & Reporting**
    - **QuickChart Integration**: Generates a live Doughnut Chart showing real-time sentiment distribution.
    - **HTML Card Widget**: Displays total analyzed volume in a clean UI.

---

## 📈 High-Value Business Use Cases

This workflow can be adapted for essential business functions:
- **Brand/Product Reputation Monitoring:** Tracking public response to new launches or negative PR incidents.
- **Early Market Risk Signal:** Providing an *early warning signal* for financial or operational risk by monitoring large-scale public sentiment shifts.
- **Competitor Intelligence:** Analyzing public reaction to competitor announcements.

---

## ⚙️ Requirements & Scalability

- **Tools:** n8n, Ollama (`llama3:latest`), Twitter API proxy, QuickChart API.
- **Scalability:** Built for continuous operation. Easily extensible with **Scheduled CRON triggers** (for real-time monitoring) and **multi-source data ingestion** (news APIs, forums, etc.).

---
