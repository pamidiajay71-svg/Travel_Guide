🌍 AI Travel Guide
An AI-powered travel companion that turns popular destinations into
personalized, multilingual audio guides. Select a destination, choose
the level of detail, pick a language and voice, and generate an
immersive guide you can listen to directly in the browser.
Features
- Explore popular Indian destinations
- Search for destinations
- AI-generated travel descriptions using Google Gemini
- AI-generated audio guides using Murf AI
- Multilingual support:
  - English
  - Hindi
  - Tamil
  - Telugu
- Summary or detailed guide modes
- Male and female voice options
- Expandable text transcript
- Responsive and modern user interface
- Flask backend with a lightweight frontend
Destinations
The current interface includes:
- Taj Mahal --- Agra
- Red Fort --- New Delhi
- Gateway of India --- Mumbai
- Hawa Mahal --- Jaipur
- Golden Temple --- Amritsar
- Mysore Palace --- Mysore
Tech Stack
Frontend
- HTML5
- JavaScript
- Tailwind CSS
- Google Fonts
Backend
- Python
- Flask
- Flask-CORS
- python-dotenv
- Requests
AI & Voice
- Google Gemini API
- Murf AI Text-to-Speech API
How It Works
User selects destination
        ↓
Choose Summary / Detailed guide
        ↓
Choose language and voice
        ↓
Frontend sends request to Flask API
        ↓
Google Gemini generates the travel guide
        ↓
Murf AI converts the guide into speech
        ↓
Backend returns text + Base64 audio
        ↓
User reads or listens to the guide
The backend exposes a /generate-audio-guide endpoint that accepts the
destination, guide type, language, voice and locale, then generates the
description and audio response.
Project Structure
Travel_Guide/
│
├── app.py
├── index.html
├── index.js
├── .env
├── .gitignore
└── README.md
Setup
1. Clone the repository
git clone https://github.com/pamidiajay71-svg/Travel_Guide.git
cd Travel_Guide
2. Create a virtual environment
python -m venv .venv
Activate it on Windows:
.venv\Scripts\activate
3. Install dependencies
pip install flask flask-cors python-dotenv requests google-genai
4. Configure environment variables
Create a .env file:
GEMINI_API_KEY=your_gemini_api_key
MURF_API_KEY=your_murf_api_key
Never commit .env or API keys to GitHub.
5. Start the backend
python app.py
The Flask API runs locally on:
http://127.0.0.1:5000
6. Open the frontend
Open index.html in your browser, or serve the frontend through a local
development server.
API
POST /generate-audio-guide
Example request:
{
  "place": "Taj Mahal",
  "answerType": "Summary",
  "language": "English",
  "voiceId": "Matthew",
  "locale": "en-US"
}
Example response:
{
  "description": "AI-generated travel description...",
  "audioBase64": "base64-encoded-audio"
}
Security
API credentials are loaded from environment variables rather than being
hard-coded into the application. Keep .env local and ensure it is
included in .gitignore.
If an API key has ever been committed to a public or remote repository,
revoke/rotate it immediately and remove the secret from Git history
before pushing again.
🚀 Future Enhancements
- Live maps and route planning
- Hotel and restaurant recommendations
- Real-time weather information
- Interactive destination maps
- Conversational voice-based travel assistant
- Personalized itineraries
- International destinations
- Progressive Web App support
- Context-aware recommendations based on trip preferences
Vision
The goal is to transform a traditional travel guide into an AI-powered
personal tour companion---one that can explain a place in your
language, in your preferred level of detail, and in a voice you enjoy.
Author
Ajay Pamidi
GitHub: https://github.com/pamidiajay71-svg
