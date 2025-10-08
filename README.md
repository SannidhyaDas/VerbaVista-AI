# 🎬 VerbaVista-AI
 YouTube Content Synthesizer using Gemini + LangChain + Streamlit

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


🔹 Step 1: Transcript Extraction
- Extracts the video’s transcript (in any supported language) using the YouTubeTranscriptApi.

🔹 Step 2: Translation (Optional)
- If the video is not in English, Gemini translates the transcript with cultural and linguistic precision.

🔹 Step 3: Processing Options
- Notes Mode → Extracts key topics and generates structured, concise notes.
- Chat Mode → Creates embeddings, stores them in Chroma DB, and launches a Retrieval-Augmented Generation (RAG) chatbot.

🔹 Step 4: RAG-based Question Answering
- When chatting, user queries are matched against the video transcript via embeddings → Gemini answers using only retrieved context.

---

## 🧰 Key Files



















## 🧠 Example Use Cases

📄 Study Companion – Quickly summarize academic or lecture videos

🎧 Podcast Assistant – Get notes or chat about podcasts and interviews

🌍 Multilingual Research Tool – Translate and analyze foreign-language videos

🏢 Enterprise Knowledge Base – Chat with company webinars or product demos


## 🧩 Future Improvements

🎙️ Add voice-based question answering (Speech-to-Text + Text-to-Speech) 

🧠 Fine-tune Gemini prompts for specialized educational content

💾 Add caching of vector stores for faster reloading

🧩 Support multiple video summarization in batches


