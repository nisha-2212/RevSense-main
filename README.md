# 🚀 RevSense – Customer Feedback Analytics & Sentiment Insights Platform

**Revsense** is an end-to-end AI-powered platform that extracts, processes, categorizes, and visualizes customer reviews from multi-source platforms to generate actionable business insights. It combines advanced NLP, real-time automation, and LLM-based reasoning to transform raw user feedback into strategic decision-making tools.

---

## 📌 Key Features

- 🔁 **Automated daily scraping** of reviews from platforms like Twitter, Play Store, App Store, and MouthShut using a scheduled Cron Job.
- 🧹 **NLP-based text preprocessing** with spaCy, including tokenization, punctuation removal, and stopword filtering.
- 🧠 **Semantic embedding generation** using Sentence-BERT (`nlptown/bert-base-multilingual-uncased-sentiment`).
- 🧭 **5-level hierarchical categorization** with 169+ unique leaf-level classes using cosine similarity.
- 📊 **Sentiment analysis** using a fine-tuned BERT model (Very Negative → Very Positive).
- 📝 **Category-wise summarization** for thematic understanding.
- 🔁 **LLM chunking strategy** for passing optimized summaries to Gemini LLM.
- ⚡ **High-speed data retrieval** with Redis database for efficient date-range queries.
- ⚙️ **FastAPI backend** for API access and front-end integration.
- 📈 **Interactive visualization dashboard** for stakeholders.

---

## ✅ Methodology & Workflow: Point-wise Explanation

1. **🕒 Daily Review Scraping**  
   - A **cron job runs every night** to scrape reviews automatically from platforms like Twitter, Play Store, App Store, and MouthShut.

2. **🧹 Review Preprocessing**  
   - Reviews are cleaned using:
     - Tokenization  
     - Stopword removal (using **spaCy**)  
     - Lowercasing  
     - Removing punctuation

3. **🧠 Embedding Generation**  
   - Preprocessed text is passed to **Sentence-BERT** (`nlptown/bert-base-multilingual-uncased-sentiment`)  
   - This generates **dense semantic vectors (embeddings)** for each review

4. **🧭 Hierarchical Category Classification**  
   - We use **cosine similarity** between review embedding and category embeddings  
   - Reviews are classified up to **5 levels of category hierarchy**  
   - Total of **169 unique leaf categories** (e.g., App crash, Delivery delay, Taste quality)

5. **🔢 Category Count & Tracking**  
   - We **count reviews per category**, helping to identify which issues occur most frequently

6. **📊 Sentiment Analysis**  
   - Using BERT model to label reviews as:
     - Very Negative  
     - Negative  
     - Neutral  
     - Positive  
     - Very Positive

7. **📝 Summary Generation**  
   - For each **category**, a **summary** of the reviews is created  
   - Helps in quickly understanding the nature of feedback

8. **🧩 Chunking for LLM Processing**  
   - The summaries are **divided into chunks** before passing to **Gemini LLM**  
   - This helps manage **token size limits** and speeds up **processing time**

9. **📈 Insight Aggregation & Visualization**  
   - Insights are grouped by **category and sentiment**  
   - Displayed on a dashboard for **stakeholders** to interpret and act on

---

## 🔗 Tech Stack

- **Languages**: Python, Bash (cron)
- **Frameworks**: FastAPI
- **Libraries**: spaCy, Sentence Transformers, HuggingFace Transformers, Redis-py, Pandas
- **LLMs**: Gemini
- **Storage**: Redis
- **DevOps**: Cron, GitHub
- **Deployment Ready**: REST APIs for front-end consumption

---

## 🧠 Sample Insights Output

- 🎯 Categories with highest volume and polarity  
- ⚠️ Emerging issues and customer pain-points  
- 🔍 Root cause analysis and customer intent  
- 📉 Predicted business impact based on review sentiment trends

---

## 💼 Use Cases

- **Product Teams** → Understand feature-level sentiment and usability bottlenecks  
- **Marketing Teams** → Gauge customer satisfaction and campaign resonance  
- **Customer Support** → Detect pain points before escalation  
- **HR/People Ops** → Analyze employee reviews from platforms like AmbitionBox

---

## 📌 Future Enhancements

- ✅ Multilingual support for global review processing  
- 🔗 CRM integration for real-time alerting  
- 📲 Expand to more review platforms (e.g., YouTube comments, Instagram DMs, etc.)

---

## 🖼️ Example Output & Results

![WhatsApp Image 2025-04-11 at 15 35 42_93ce7db0](https://github.com/user-attachments/assets/5270997a-e1ff-4685-a258-cb5fe9b9556a)
![WhatsApp Image 2025-04-11 at 15 35 41_64157dc2](https://github.com/user-attachments/assets/9aab7848-23f8-473a-a66a-8a29bcf7e35c)
![WhatsApp Image 2025-04-11 at 15 35 41_2149c581](https://github.com/user-attachments/assets/1c2ecc9b-b42f-423f-a67e-21c13b12db6f)
![WhatsApp Image 2025-04-11 at 15 42 33_238f8a1a](https://github.com/user-attachments/assets/6e4f7829-7cb7-43a9-b60b-a4bbdfca7e6c)

- API Response...
![image](https://github.com/user-attachments/assets/0e8f3e67-fed2-4e42-be66-acca702207aa)

---



## 🚦 How to Run This Project

### 1. Clone the Repository
```sh
git clone https://github.com/VedantPancholi/RevSense.git
cd RevSense
```

### 2. Install Frontend (Next.js) Dependencies
```sh
yarn install
# or
npm install
```

### 3. Start the Next.js Frontend
```sh
yarn dev
# or
npm run dev
```
The frontend will be available at [http://localhost:3000](http://localhost:3000).

### 4. Set Up and Run the FastAPI Backend
Navigate to the backend directory and install Python dependencies:
```sh
cd app/fastApi
pip install -r ../../requirements.txt
```
Run the FastAPI server:
```sh
uvicorn app:app --reload --port 8000
```
The backend API will be available at [http://localhost:8000](http://localhost:8000).

### 5. Configuration
- Edit `.env.local` and other config files as needed for your environment.

### 6. Access the Application
- Open your browser and go to [http://localhost:3000](http://localhost:3000) for the dashboard.
- The FastAPI backend endpoints will be available at [http://localhost:8000](http://localhost:8000).

---


