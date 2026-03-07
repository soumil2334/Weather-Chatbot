# Weather Alert Chatbot

A conversational weather assistant that answers weather-related questions and sends push notifications to your device via Pushover.

## What It Does

- Accepts natural language weather queries (e.g. *"How's the weather in Delhi?"*, *"Should I carry an umbrella?"*)
- Fetches real-time weather data from the OpenWeather API
- Uses Gemini 2.0 Flash (via OpenAI-compatible SDK) to interpret the data and generate a friendly response
- Sends a short push notification to your device via Pushover whenever a new city is queried
- Remembers the last city discussed, so follow-up questions don't need to repeat it

## Prerequisites

- Python 3.8+
- A [Pushover](https://pushover.net/) account (app token + user key)
- An [OpenWeather](https://openweathermap.org/api) API key
- A [Google Gemini](https://aistudio.google.com/) API key

## Setup

1. **Install dependencies**
   ```bash
   pip install requests openai gradio python-dotenv
   ```

2. **Create a `.env` file** in the project root:
   ```env
   PUSHOVER_TOKEN=your_pushover_app_token
   PUSHOVER_USER=your_pushover_user_key
   OPENWEATHER=your_openweather_api_key
   GOOGLE_GEMINI=your_gemini_api_key
   ```

3. **Update the device name** in `push()` if needed:
   ```python
   'device': 'YourDeviceName'
   ```

## Running

```bash
python weather_bot.py
```

This launches a Gradio chat interface in your browser. Type any weather-related question to get started.

## Example Queries

- *"What's the weather like in Tokyo?"*
- *"Is it a good day for cricket in Mumbai?"*
- *"Should I bring a jacket?"* (after a city has been mentioned)
