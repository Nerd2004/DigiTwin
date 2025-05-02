
# DigiTwin 🧠🎭

**DigiTwin** is an open-source, AI-powered project that allows you to create realistic digital avatars from static images and voice input using freely available models and tools. Designed entirely in Google Colab for accessibility, DigiTwin combines state-of-the-art technologies like **SadTalker**, **Mistral 7B**, and **XTTS** to generate lifelike videos of digital humans speaking your desired input.

---

## 🚀 Features

- 📸 **Photo-to-Video** generation using SadTalker
- 🔊 **Voice Cloning** using XTTS
- 🧠 **Personality-based Response Generation** using a quantized Mistral 7B model (via RAG)
- 🌐 **Flask + Ngrok API** for video generation
- 🧪 All-in-one Colab notebooks — no local setup required

---

## 🧰 Tech Stack

| Tool        | Role                                 |
|-------------|--------------------------------------|
| **SadTalker** | Converts static image + audio into video |
| **XTTS**     | Voice synthesis (cross-lingual)      |
| **Mistral 7B** | Response generation (quantized for speed) |
| **LlamaIndex** | Retrieval-Augmented Generation pipeline |
| **Flask + Ngrok** | API and tunneling server for interaction |
| **Google Colab** | Development environment           |

---

## 📁 Project Structure

| Notebook               | Description                                                        |
|------------------------|--------------------------------------------------------------------|
| `Videogen.ipynb`       | Contains SadTalker setup, image/audio upload, and video generation |
| `RAG&Voice.ipynb`      | Handles RAG-based response generation and XTTS-based audio cloning |

---
## 🎥 Demo

👉 [Watch the Video Demo](https://youtu.be/qoyp2dIhWEE)


Or preview below:

<video src="https://youtu.be/qoyp2dIhWEE" controls width="600"></video>


## ⚙️ Setup Instructions

### 🌩️ Run in Google Colab

Click to launch:

- [Videogen.ipynb](LINK_TO_YOUR_COLAB)
- [RAG&Voice.ipynb](LINK_TO_YOUR_COLAB)

### 🔧 Requirements

Google Colab will install all dependencies. Make sure:
- GPU is enabled via **Runtime → Change runtime type → GPU**
- You update any Python versions / CUDA compatibility as prompted

---

## 🧪 API Usage (via Flask + Ngrok)

The `Videogen` notebook sets up a Flask API served via ngrok with 3 endpoints:

1. **`POST /generate`**
   - Form-data: `image` (.jpg), `audio` (.wav)
   - Returns: `job_id`

2. **`GET /status/<job_id>`**
   - Returns job status: `processing`, `completed`, or `failed`

3. **`GET /download/<job_id>`**
   - Returns generated `.mp4` video for successful jobs

**Note:** Add header: `ngrok-skip-browser-warning: true` to all requests.

---

## 🧠 How It Works

1. **RAG Pipeline**:
   - A user provides a question
   - Relevant chunks are retrieved from a text-based memory (tweets, persona, etc.)
   - Mistral 7B generates a personality-driven response

2. **Voice Cloning**:
   - The response is passed to XTTS to synthesize the audio

3. **Video Generation**:
   - Image + cloned audio is passed to SadTalker to generate a video

---

## 🎯 Use Cases

- AI influencers & spokespersons
- Personalized digital avatars
- Chatbot agents with faces
- Educational explainers
- AI therapists / assistants

---

## 📌 Example Output

| Input | Output |
|-------|--------|
| Image (.jpg) + Audio (.wav) | Talking head `.mp4` video |
| Text question | Personality-driven spoken video response |

---

## 🔐 Disclaimer

This project is for **educational and research purposes only**. Be mindful of ethical implications when creating digital avatars.

---

## 🙌 Acknowledgements

- [SadTalker](https://github.com/OpenTalker/SadTalker)
- [XTTS](https://github.com/coqui-ai/TTS)
- [Mistral 7B](https://huggingface.co/mistralai/Mistral-7B-v0.1)
- [LlamaIndex](https://github.com/jerryjliu/llama_index)
