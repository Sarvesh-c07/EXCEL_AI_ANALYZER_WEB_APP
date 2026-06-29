# Excel AI Analyzer

A powerful web application that allows you to upload multiple Excel/CSV files and analyze them using AI through text or voice commands. Supports multiple free AI APIs with automatic fallback.

## Features

- **Multiple File Upload**: Upload multiple Excel (.xlsx, .xls) and CSV files at once
- **Multi-API AI Analysis**: Supports Gemini, Groq, and OpenRouter with auto-fallback
- **Voice Commands**: Speak your queries using built-in speech-to-text
- **Text Queries**: Type your questions in plain English
- **Download Results**: Export analysis results as Excel files
- **File Preview**: Preview uploaded file data before querying
- **Dark Theme**: Modern, professional dark UI

## Supported AI APIs (Free Tiers)

| API | Free Tier | Sign Up | Speed |
|---|---|---|---|
| **Groq** | Very generous, no credit card | [console.groq.com](https://console.groq.com/keys) | Fastest |
| **Gemini** | 60 requests/minute | [aistudio.google.com](https://aistudio.google.com/app/apikey) | Fast |
| **OpenRouter** | Many free models | [openrouter.ai](https://openrouter.ai/settings/keys) | Medium |
| **Local (Pandas)** | Always free, no API needed | Built-in | Instant |

## Setup Instructions

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Get API Keys (At least one recommended)

**Recommended: Groq (Fastest, most generous free tier)**
1. Go to [console.groq.com/keys](https://console.groq.com/keys)
2. Sign up (no credit card required)
3. Create API Key
4. Copy and paste in the app

**Alternative: Gemini**
1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with Google
3. Create API Key

**Alternative: OpenRouter**
1. Go to [openrouter.ai/settings/keys](https://openrouter.ai/settings/keys)
2. Sign up
3. Create API Key

### 3. Run the Application

```bash
python app.py
```

Or use the auto-start scripts:
- **Windows**: Double-click `start.bat`
- **Linux/Mac**: `./start.sh`
- **Any OS**: `python start.py`

The app will run on `http://localhost:5000`

## How It Works

1. **Upload Files**: Drag & drop or select Excel/CSV files
2. **Add API Keys**: Paste at least one API key (keys are saved locally in your browser)
3. **Ask Questions**:
   - **Type**: Enter queries like "Show me top 10 customers by sales"
   - **Voice**: Click microphone and speak your query
4. **Auto-Fallback**: If one API quota is exceeded, the app automatically tries the next one
5. **View Results**: See analysis table with insights
6. **Download**: Click "Download Excel" to save results

## Example Queries

- "Show me top 10 products by revenue"
- "Filter premium customers from Mumbai"
- "Revenue by category last quarter"
- "Which city has the most orders?"
- "Show records where destination is Sharjah"
- "Show total sales by month"
- "Filter customers with orders greater than 100"

## Project Structure

```
excel-ai-analyzer/
├── app.py                 # Flask backend with multi-API support
├── requirements.txt       # Python dependencies
├── start.bat              # Windows auto-start
├── start.sh               # Linux/Mac auto-start
├── start.py               # Cross-platform auto-start
├── templates/
│   └── index.html        # Main UI template
├── static/
│   ├── css/
│   │   └── style.css     # Stylesheet
│   └── js/
│       └── app.js        # Frontend logic
└── uploads/              # Temporary upload folder
```

## Troubleshooting

### "Quota exceeded" error
- The app will automatically try the next API key you provided
- Add multiple API keys for seamless experience
- If all APIs fail, the app falls back to local pandas processing

### "No module named X" error
- Delete the `venv` folder and run `start.bat` again
- Or run: `python -m pip install -r requirements.txt`

### API Key not working
- Make sure you copied the full key (no extra spaces)
- Check if the key has been used too many times (free tier limits)
- Try a different API provider

## Notes

- API keys are stored in your browser's localStorage (never sent to our servers except for analysis)
- The app works without any API key using local pandas processing (limited features)
- Supports files up to 50MB total
- Speech recognition works best in Chrome/Edge browsers
