# LiveKit AI Voice Assistant

## Overview

This project is a real-time AI Voice Assistant built using LiveKit Agents.

The assistant listens to user speech, converts it to text, generates intelligent responses using Gemini, and speaks back using natural-sounding voice synthesis.

### Technology Stack

- LiveKit Agents
- AssemblyAI (Speech-to-Text)
- Google Gemini 2.5 Flash (LLM)
- Cartesia Sonic-2 (Text-to-Speech)
- Python

---

## Architecture

```text
User Speech
     │
     ▼
AssemblyAI STT
     │
     ▼
Gemini 2.5 Flash
     │
     ▼
Cartesia Sonic-2
     │
     ▼
Voice Response
```

---

## Features

- Real-time voice conversations
- Fast speech recognition
- AI-powered responses
- Natural voice synthesis
- Interruptible conversations
- Technology and general knowledge assistance
- Interview preparation support
- Software engineering guidance

---

## Project Structure

```text
livekit-demo/
│
├── agent.py
├── .env
├── requirements.txt
└── README.md
```

---

## Prerequisites

- Python 3.10+
- LiveKit Cloud Account
- AssemblyAI API Key
- Gemini API Key
- Cartesia API Key

---

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd livekit-demo
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the environment:

### macOS/Linux

```bash
source venv/bin/activate
```

### Windows

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file:

```env
LIVEKIT_URL=wss://your-livekit-url
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret

ASSEMBLYAI_API_KEY=your_assemblyai_api_key

GOOGLE_API_KEY=your_gemini_api_key

CARTESIA_API_KEY=your_cartesia_api_key
```

---

## Running the Agent

Start the agent:

```bash
python agent.py dev
```

The worker will connect to LiveKit and wait for participants to join.

---

## Testing the Agent

### Option 1: LiveKit Agents Playground (Recommended)

1. Start the agent:

```bash
python agent.py dev
```

2. Open the LiveKit Playground URL from your LiveKit Cloud dashboard.

3. Join a room.

4. Allow microphone access.

5. Start speaking to the assistant.

Example questions:

- What is Artificial Intelligence?
- Explain RAG in simple terms.
- What is the difference between SQL and NoSQL?
- Ask me a Python interview question.

---

### Option 2: LiveKit Console

1. Login to your LiveKit Cloud account.

2. Navigate to:

```text
Project → Agents → Playground
```

3. Create or join a room.

4. Connect to the room.

5. Verify that:

- Microphone input is detected.
- Speech is transcribed by AssemblyAI.
- Gemini generates a response.
- Cartesia speaks the response.

---

### Expected Flow

```text
User Speech
    ↓
AssemblyAI STT
    ↓
Gemini 2.5 Flash
    ↓
Cartesia TTS
    ↓
Audio Response
```

---

### Troubleshooting

#### No Speech Recognition

Verify:

```env
ASSEMBLYAI_API_KEY=your_key
```

#### No AI Response

Verify:

```env
GOOGLE_API_KEY=your_key
```

Check for quota or billing errors.

#### No Voice Output

Verify:

```env
CARTESIA_API_KEY=your_key
```

#### Agent Not Connecting

Verify:

```env
LIVEKIT_URL=
LIVEKIT_API_KEY=
LIVEKIT_API_SECRET=
```

and ensure the worker is running.

---

### Demo Scenario

Try asking:

> Hello, who are you?

> Explain Machine Learning.

> What is a Vector Database?

> Ask me a Python interview question.

> Explain Retrieval-Augmented Generation.

This demonstrates the complete real-time voice pipeline powered by LiveKit, AssemblyAI, Gemini, and Cartesia.