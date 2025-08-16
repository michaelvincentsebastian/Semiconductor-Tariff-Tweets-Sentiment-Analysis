# Trump 100% Tariff Sentiment Analysis – n8n Workflow

This n8n workflow automates **sentiment analysis on Twitter data** related to "Trump semiconductor tariffs" and generates aggregated statistics with visual outputs.  

---

## 🔄 Workflow Overview

1. **Trigger**  
   - Starts manually using the `Manual Trigger` node.

2. **Twitter Data Pulling**  
   - Fetches tweets from a Twitter API (`twitterapi.io`) using the query:  
     ```
     trump semiconductor tariffs
     ```
   - Supports pagination (fetches limited number of pages).

3. **Cleaning**  
   - Extracts only essential tweet fields:
     - Tweet ID  
     - URL  
     - Text  
     - Username  

4. **Sentiment Classification**  
   - Uses an **LLM (via Ollama + LangChain)** to classify each tweet as:
     - `positive`
     - `negative`
     - `neutral`  
   - Prompt is designed to be **strict and concise** (only one-word outputs).

5. **Formatting**  
   - Ensures clean sentiment outputs:
     - Normalizes to lowercase.  
     - Removes any extra characters (handles sarcasm, typos, etc.).

6. **Data Aggregation**  
   - Counts and calculates percentages of each sentiment category:
     - Total tweets  
     - Positive %  
     - Negative %  
     - Neutral %  

7. **Visualization & Output**  
   - **QuickChart Doughnut Chart**: Creates a distribution chart of sentiment percentages.  
   - **HTML Card Widget**: Displays total tweet count in a styled card format.  

---

## 📊 Example Output

- **Doughnut Chart**:  
  Visual breakdown of sentiment percentages (`positive`, `negative`, `neutral`).  

- **HTML Card**:  
  Shows total tweets analyzed in a clean card UI.  

---

## ⚙️ Requirements

- **n8n** (self-hosted or cloud)  
- **Ollama** running locally with `llama3:latest` model installed  
- **API Access**:
  - Twitter API proxy (`twitterapi.io`)  
  - QuickChart API  

---

## 🔑 Credentials Needed

- **Twitter API Key** (HTTP Header Auth)  
- **Ollama API** (Local service key)  

---

## 🚀 Use Case

This workflow can be adapted for:  
- Tracking sentiment on political/economic news.  
- Brand or product reputation monitoring on Twitter.  
- Social listening dashboards with live charts.  

---

## 📝 Notes

- Currently configured for **manual runs**.  
- Can be extended with:
  - Scheduled triggers (cron).  
  - More advanced NLP (entity detection, sarcasm handling).  
  - Multi-source data (news, forums, etc.).  

---
