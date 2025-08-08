# 🧙‍♂️ Interactive Storytelling AI (POC)

This project is a **proof of concept (POC)** for an interactive storytelling web app where users co-create a story by playing a role in it. The system uses an AI model (like GPT) to generate the narrative, and a separate image generation service (like DALL·E or Stable Diffusion) to create character illustrations.

## 🎯 Project Goal

Allow users to:
- Input their actions and dialogue as part of a dynamic, unfolding story.
- Interact with AI-generated characters and events.
- See generated images of the characters they encounter.

## 📦 Tech Stack (Current POC)

| Component | Tech |
|----------|------|
| Frontend | React (planned) |
| Backend API | Node.js/Express or Python/Flask |
| LLM | Gemini (via API) |
| Image Generation | Google Vision (planned) |
| Storage | In-memory or simple JSON file (for now) |

## 🧠 How It Works (Current Flow)

1. **User submits an action/input** via a frontend or terminal.
2. **Backend builds a prompt** using story history and user input.
3. The prompt is sent to **GEMINI** to generate the next part of the story.
4. If a new character is detected, a **placeholder image prompt** is generated.
5. The story and metadata are saved to memory (or file).
6. The updated story is sent back to the frontend.

## 🖼 Image Generation Plan

> Not yet implemented in this POC

When a new character appears:
- Backend queues a job to generate the character's image (based on description from GEMINI).
- An image generation service (Google Vision) is called.
- Image is stored (e.g. Database or local folder), and linked to that character in the story.

## 🗂 Example Folder Structure

```
/story-ai-poc
│
├── backend/
│   ├── server.js or app.py
│   ├── story_engine.js
│   └── character_detector.js
│
├── prompts/
│   └── system.txt
│
├── storage/
│   └── story_sessions.json
│
└── README.md
```

## 🧪 Example Interaction

```
User: I walk into the dark forest.

AI: You step into the shadowy forest, trees whispering overhead. Suddenly, a cloaked figure blocks your path.

User: I ask him who he is.

AI: The figure lowers his hood. "I am Thorne, guardian of the Black Pines."
```

(Thorne would now be queued for image generation.)


Made with ❤️ for creative storytellers.
