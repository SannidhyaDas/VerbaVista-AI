# 🎬 VerbaVista-AI ( [ 🌐Live Demo ](https://sannidhya-das-verbavista-ai.streamlit.app/) )
 YouTube Content Synthesizer using Gemini + LangChain + Streamlit
![VideoChat eg](https://github.com/SannidhyaDas/VerbaVista-AI/blob/main/assets/appInterface_1.png)

![VideoNotes eg](https://github.com/SannidhyaDas/VerbaVista-AI/blob/main/assets/appInterface_2.png)
> 🚀 Transform any YouTube video into **structured notes** or **an interactive chatbot** powered by Google Gemini and LangChain.

---

## 📖 Overview

**VidSynth AI** is a **Generative AI application** that automatically fetches a YouTube video transcript, translates it (if needed), and turns it into:

- 🧠 **Structured Notes** – AI-generated, topic-wise summaries  
- 💬 **Interactive Chatbot** – Ask questions directly about the video content  

It’s built using **LangChain**, **Google Gemini 2.5 Flash**, and **Streamlit**, enabling seamless text extraction, translation, chunking, and contextual question answering — all in one elegant app.

---

## ✨ Key Features

| Feature | Description |
|----------|-------------|
| 🎥 **YouTube Transcript Fetching** | Automatically extracts video transcripts in multiple languages using `YouTubeTranscriptApi`. |
| 🌐 **Multilingual Translation** | Uses Gemini LLM to translate transcripts into English while preserving tone and meaning. |
| 🧩 **Chunking & Embeddings** | Splits long transcripts and creates embeddings using `GoogleGenerativeAIEmbeddings`. |
| 💾 **Vector Store (RAG)** | Stores embeddings in a **Chroma** vector database for fast, context-based retrieval. |
| 🗂️ **AI Notes Generator** | Creates structured, human-readable notes using LLM prompting. |
| 💬 **Chat with Video** | Chatbot mode lets users ask natural language questions about any video content. |
| 🧠 **Exponential Backoff Handling** | Handles Google API quota limits gracefully with retry logic. |

---

## 🧱 Tech Stack

| Category | Tools / Libraries |
|-----------|-------------------|
| 💡 **LLM** | [Gemini 2.5 Flash Lite](https://ai.google.dev/) via LangChain |
| 🧩 **Frameworks** | [LangChain](https://www.langchain.com/), [Streamlit](https://streamlit.io/) |
| 🔤 **Embeddings** | `GoogleGenerativeAIEmbeddings` |
| 🗄️ **Vector DB** | [Chroma](https://docs.trychroma.com/) |
| 🎞️ **Transcript Extraction** | [YouTubeTranscriptApi](https://pypi.org/project/youtube-transcript-api/) |
| ⚙️ **Other Utilities** | `dotenv`, `regex`, `time`, `google.api_core.exceptions` |

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/SannidhyaDas/VerbaVista-AI.git
cd VerbaVista-AI
```
### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```
### 3️⃣ Add Environment Variables

Create a .env file in the root directory with your Google API Key:
```ini
GOOGLE_API_KEY=your_google_api_key_here
```
> 🔑 You can get your key from [Google AI Studio](https://aistudio.google.com/)

### 🚀 Run the App
```bash
streamlit run app.py
```
Then open your browser at the link Streamlit provides (usually http://localhost:8501).

---

## 🧩 How It Works — Behind the Scenes

![pipeline](https://github.com/SannidhyaDas/VerbaVista-AI/blob/main/assets/VerbaVista-pipeline.png)

🔹 **Step 1: Transcript Extraction** - Extracts the video’s transcript (in any supported language) using the YouTubeTranscriptApi.

🔹 **Step 2: Translation (Optional)** - If the video is not in English, Gemini translates the transcript with cultural and linguistic precision.

🔹 **Step 3: Processing Options**
- Notes Mode → Extracts key topics and generates structured, concise notes.
- Chat Mode → Creates embeddings, stores them in Chroma DB, and launches a Retrieval-Augmented Generation (RAG) chatbot.

🔹 **Step 4: RAG-based Question Answering** - When chatting, user queries are matched against the video transcript via embeddings → Gemini answers using only retrieved context.

---

## 🧰 Key Files

```bash
VerbaVista-AI/
│
├── assets/                        # Streamlit web interface
│   ├── appInterface_1.png            # Chat with Video example 
│   ├── appInterface_2.png            # Notes from the video example 
│   └── VerbaVista-pipeline           # working pipeline
│
├── deployment/             # Streamlit deployment setup
│   ├── requirements.txt            # Python dependencies
│   ├── main.py             # Core logic and LLM pipelines  
│   └── app.py              # Streamlit user interface
│
├── localhost/              # setup to run app locally
│   ├── requirements.txt            # Python dependencies
│   ├── main.py             # Core logic and LLM pipelines
│   └── app.py              # Streamlit user interface
│
└── README.md                   # Project documentation

```

## 🧠 Example Use Cases  

#### 📚 **Smart Study Companion** - Transform complex **academic or lecture videos** into clear, structured notes for faster learning and revision.  

#### 🎧 **Podcast & Interview Analyst** - Extract **key takeaways and actionable insights** from long-form conversations — save hours of manual listening.  

#### 🌐 **Multilingual Research Assistant** - Break **language barriers** by translating, summarizing, and analyzing global video content in real time.  

#### 🏢 **Enterprise Knowledge Hub** - Turn webinars, product demos, and training sessions into **searchable, chat-enabled knowledge bases** for internal teams.  

#### 💼 **Scalable Business Value** - Integrate with CRMs or content libraries to **automate learning, onboarding, and support**, turning video data into **searchable, revenue-driving intelligence**.  

---

## 🧩 Future Improvements  

#### 🎙️ **Voice Interaction** - Add **Speech-to-Text and Text-to-Speech** modules for fully voice-based question answering.  

#### 🧠 **Enhanced Prompt Tuning** - Fine-tune **Gemini prompts** for domain-specific or educational content understanding.  

#### 💾 **Vector Store Caching** - Implement caching for **faster reloads and reduced embedding costs**.  

#### 🧩 **Batch Video Summarization** - Enable **multi-video summarization** to process and analyze playlists or course modules efficiently.  


