# 🧳 Smart Trip Preparation Assistant (India)

This is a Streamlit-based module that acts as a **Smart Trip Preparation Assistant** for Indian travellers.
It is designed to plug into a larger AI-powered travel recommendation system.

## 🔍 What it does

### 1. Weather-aware Packing List
- Takes:
  - Destination coordinates (lat, lon)
  - Trip dates (start & end)
  - Trip type (Trek / Beach / City / Roadtrip / Religious / Workcation)
  - Style (Solo / Family / Adventure / Work)
- Uses the **Open-Meteo** API to fetch real weather data.
- Classifies the weather into bands: `Freezing / Cold / Mild / Warm/Hot`.
- Generates a **smart packing list** using:
  - Weather (temperature + rain)
  - Trip type (trek, beach, roadtrip, etc.)
  - Style (solo, family, work)
  - Trip duration (short / medium / long)

The packing list is shown as **categorized checklists** in Streamlit (Essentials, Clothes, Weather Protection, Trip-specific, etc.).

### 2. Indian Holiday + Leave Planner

- Uses the **Nager.Date** public holiday API for India (country code `IN`).
- Assumes a typical **Mon–Fri office job** with **Sat–Sun off**.
- Asks the user for:
  - Year to plan for
  - Maximum leave days they can take at once (e.g. 1–3)
- Scans the calendar and finds smart windows where:
  - Weekends + public holidays + a few leave days
  - Give the **maximum continuous vacation days**
- Outputs suggestions like:
  - “Option 1: 2025-08-14 → 2025-08-17 (4 days total, 1 leave day, includes Independence Day)”

This makes the module **context-aware for Indian office workers**.

## 🛠 Tech Stack

- **Frontend / App**: Streamlit (Python)
- **APIs**:
  - Weather: [Open-Meteo](https://open-meteo.com/)
  - Indian Holidays: [Nager.Date](https://date.nager.at/)
- **Language**: Python 3

## 🚀 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/rashiuwu/smart-trip-prep.git
   cd smart-trip-prep

2. Install dependencies:
 ```bash
pip install -r requirements.txt

3. Run the Streamlit app:
 ```bash
streamlit run trip_prep_page.py

4. Open the link shown in the terminal (usually http://localhost:8501).