# Study Assistant

An AI-powered study assistant built with Gradio and Google's Gemini API. Ask any question and get an explanation in the personality of your choice.

## Features

- Ask questions on any topic and get beginner-friendly explanations
- Choose a personality:
  - **Friendly**: enthusiastic, encouraging, uses analogies and real-world examples
  - **Academic**: formal and detailed, in the style of a university professor
- Every answer ends with a follow-up question to check your understanding
- Simple web interface built with Gradio

## Tech Stack

- Python
- [Gradio](https://www.gradio.app/) for the web UI
- [Google Gen AI SDK](https://pypi.org/project/google-genai/) (Gemini) for responses
- [Render](https://render.com/) for deployment

## Project Structure

```
.
├── app.py             # Gradio app and Gemini logic
├── requirements.txt   # Python dependencies
└── README.md
```

## Run Locally

1. Clone the repository and move into it:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set your Gemini API key as an environment variable:
   ```bash
   # macOS / Linux
   export GEMINI_API_KEY="your-api-key"

   # Windows (PowerShell)
   $env:GEMINI_API_KEY="your-api-key"
   ```
4. Start the app:
   ```bash
   python app.py
   ```
5. Open http://localhost:7860 in your browser.

## Deploy on Render

1. Push `app.py`, `requirements.txt` and this README to a GitHub repository.
2. On Render, click **New → Web Service** and select your repository.
3. Use these settings:
   - **Runtime:** Python 3
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `python3 app.py`
   - **Instance Type:** Free
4. Add an environment variable:
   - **Key:** `GEMINI_API_KEY`
   - **Value:** your Gemini API key
5. Click **Create Web Service**. Once the build finishes, you'll get a public URL like `https://your-app-name.onrender.com`.

## Notes

- Never commit your API key to GitHub. Keep it in environment variables only.
- On Render's free tier, the app sleeps after about 15 minutes of inactivity, so the first visit after a break can take up to a minute to load.
- The app reads the port from the `PORT` environment variable that Render provides, and falls back to 7860 locally.

## Author

James Nicholas
