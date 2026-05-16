# ✈️ AI-Travel-Planer

An AI-powered multilingual travel assistant that collects trip preferences through natural conversation and generates a complete, personalized travel itinerary. Supports both **English** and **Chinese (中文)**.

---

## Overview

AI-Travel-Planer is a conversational travel planning system where an AI assistant named **Martin** guides users through a friendly, natural dialogue to understand their travel needs — then compiles everything into a structured trip plan ready for itinerary generation.

The assistant intelligently collects trip details step by step, handles mid-conversation changes, confirms all details before finalizing, and outputs a clean summary of the trip profile.

---

## How It Works

The assistant follows a two-phase flow:

**Phase 1 — Preference Collection**

Martin engages the user in conversation and progressively collects the following:

| Field | Description |
|---|---|
| **Destination** | Where the user is traveling to |
| **Origin** | Where they are departing from |
| **Traveling With** | Who is joining and total traveler count |
| **Travel Dates** | When the trip starts |
| **Duration** | How many days the trip lasts |
| **Purpose** | Type of trip — leisure, business, cultural, foodie, etc. |
| **Transportation** | Preferred mode of travel within the destination |

**Phase 2 — Confirmation & Finalization**

Once all fields are collected, Martin presents a full summary for user confirmation. Users can make natural language edits (e.g. "change the duration to 10 days") and the assistant updates accordingly — then re-confirms before generating the final trip profile.

A trip description is automatically generated from the full conversation to capture motivations, preferences, and experience goals for downstream itinerary planning.

---

## Key Features

- Conversational AI assistant with distinct personality and tone (Martin from Travel Labs)
- Multilingual support — English and Chinese, selectable at initialization
- Smart information extraction from natural language using LLMs
- Handles mid-conversation corrections and field updates gracefully
- Confirms all details before finalizing — users can edit anything before locking in
- Auto-generates a rich trip description from conversation context
- Fuzzy date parsing — understands inputs like "second week of next month"
- Outputs a clean JSON trip profile on confirmation

---

## Tech Stack

- **Language:** Python 3.8+
- **AI:** OpenAI GPT-4 Turbo
- **Language Support:** English, Chinese (via GPT multilingual understanding)
- **APIs:** Booking.com (integration-ready), Google Places
- **Date Parsing:** `python-dateutil`
- **Interface:** CLI (web/app integration-ready via modular `TravelChatbot` class)

---

## Project Structure

```
AI-Travel-Planer/
├── main.py          # Core chatbot logic — TravelChatbot class and CLI runner
├── booking.py       # Booking.com API integration
├── opentest.py      # OpenAI connection testing
├── test.py          # General test scripts
├── .gitignore
└── LICENSE
```

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/AI-Travel-Planer.git
cd AI-Travel-Planer
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up your `.env` file

```
OPENAI_API_KEY=your_openai_api_key
TRAVEL_API_KEY=your_booking_api_key
```

### 4. Run the assistant

```bash
python main.py
```

---

## Sample Output (Trip Profile JSON)

```json
{
  "travel_info": {
    "from": "Dhaka, Bangladesh",
    "to": "Tokyo, Japan",
    "traveling_with": "2 people (couple)",
    "when": "second week of June (2025-06-08)",
    "duration": "10 days",
    "purpose": "sightseeing and cultural exploration",
    "transportation": "trains and public transit",
    "descriptions of the trip": "A couple seeking an immersive cultural experience..."
  },
  "status": "complete",
  "missing_info": [],
  "confirmed": true
}
```

---

## Supported Travel Purposes

The `purpose` field accepts any free-text description. Common examples include:

| Category | Examples |
|---|---|
| **Leisure** | Sightseeing, beach holiday, relaxation, honeymoon |
| **Cultural** | Heritage tours, museum visits, local cuisine exploration |
| **Adventure** | Hiking, trekking, outdoor activities |
| **Business** | Conferences, corporate travel, networking |
| **Family** | Family vacation, theme parks, kid-friendly activities |
| **Solo** | Backpacking, self-discovery, solo exploration |

---

## Future Roadmap

- Real-time hotel and flight price fetching
- Full Booking.com and Skyscanner integration
- Day-by-day itinerary generation from the trip profile
- Map view of the planned itinerary
- Save and share travel plans
- Mobile app and web interface support
- Personal travel dashboard

---

## License

Licensed under the [MIT License](https://github.com/BusraRafa/AI-Travel-Planner/blob/main/LICENSE).
