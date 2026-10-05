# AgriEdge

A Smart Irrigation Management and Monitoring System built with Next.js, FastAPI, Supabase, and ESP32. AgriEdge helps farmers monitor field conditions, optimize irrigation, and receive AI-powered agricultural guidance in real time.

## Overview

AgriEdge combines:
- a modern Next.js web dashboard for monitoring and controls,
- a FastAPI backend for AI-driven analytics and sensor integration,
- Supabase for data storage and retrieval,
- Gemini AI for natural-language crop and irrigation assistance,
- ESP32-connected sensors for real-world field monitoring.

The project is designed to provide actionable insights for irrigation scheduling, soil condition checks, and operational efficiency in smart farming environments.

## Features

- Real-time irrigation and sensor monitoring
- Smart crop health and soil condition insights
- AI-powered farming assistant using Gemini
- Multi-language support for farmer assistance
- Dashboard for farm status and operational summaries
- Sample analytics and sensor trend analysis
- Authentication-ready frontend using Clerk
- Responsive UI built with Next.js and Tailwind CSS

## Tech Stack

### Frontend
- Next.js 15
- React 19
- Tailwind CSS
- shadcn/ui components
- Framer Motion
- Recharts

### Backend
- Python
- FastAPI
- Pydantic
- Supabase client
- Pandas
- Google Generative AI

### Hardware / Data Layer
- ESP32
- Supabase database
- Sensor telemetry ingestion

## Project Structure

```text
AgriEdge/
├── README.md
├── agriedge/                  # Next.js frontend
│   ├── app/                  # App routes and pages
│   ├── components/           # UI components
│   ├── hooks/                # React hooks
│   ├── lib/                  # Shared logic/utilities
│   ├── utils/                # Helper functions and motion configs
│   ├── public/               # Static assets
│   ├── package.json          # Frontend dependencies and scripts
│   ├── next.config.ts
│   ├── tailwind.config.ts
│   └── tsconfig.json
├── backend/                  # FastAPI backend
│   ├── main.py               # API server and AI logic
│   ├── requirements.txt      # Python dependencies
│   └── venv/                 # Local virtual environment
└── .gitignore
```

## Frontend Application

The frontend is located in `agriedge/` and includes pages such as:
- landing page
- dashboard
- chatbot interface
- sign-in flow
- settings and monitoring logs
- about page

The main landing experience is designed as a smart farming product page with team information, feature highlights, and call-to-action buttons.

## Backend API

The backend is built in `backend/main.py` and exposes the following routes:

- `POST /ask` – Ask a question about agricultural conditions and get a Gemini-powered response
- `GET /health` – Health check endpoint
- `GET /sample-data` – Returns sample sensor data and analysis

The backend also includes:
- Supabase integration
- sensor data fallback analysis
- language-aware AI responses in English and major Indian languages
- sample data insights for irrigation recommendations

## Environment Variables

Create environment variables for the backend before running the API.

### Backend `.env`

```env
GEMINI_API_KEY=your_gemini_api_key
SUPABASE_URL=your_supabase_project_url
SUPABASE_KEY=your_supabase_anon_or_service_key
```

If your frontend uses Clerk authentication, configure the corresponding `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` and Clerk secret variables in your frontend environment as required by your deployment setup.

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- Python 3.10+
- A Supabase project
- A Gemini API key
- Optional: ESP32 sensor setup and deployment environment

### 1) Install Frontend Dependencies

```bash
cd agriedge
npm install
```

Run the frontend in development mode:

```bash
npm run dev
```

Open http://localhost:3000 in your browser.

### 2) Install Backend Dependencies

```bash
cd backend
python -m venv venv
source venv/bin/activate   # Linux/macOS
# or
venv\Scripts\activate      # Windows
pip install -r requirements.txt
```

Run the backend:

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

The API will be available at:
- http://localhost:8000/health
- http://localhost:8000/docs

## Example Usage

### Ask the AI assistant

```bash
curl -X POST http://localhost:8000/ask \
  -H "Content-Type: application/json" \
  -d '{
    "question": "Is my field sufficiently irrigated right now?",
    "language": "english"
  }'
```

## Deployment Notes

This project is structured for easy deployment across separate frontend and backend services:
- Frontend: Vercel or any Next.js hosting platform
- Backend: Render, Railway, Fly.io, or a Python hosting provider
- Database: Supabase

## Team

This project includes team members represented in the landing page UI:
- Mithil Girish
- Vaibhav PK
- Sebabrat

## Notes

The project is an academic and prototype smart agriculture solution focused on precision irrigation, environmental monitoring, and AI-based recommendations.

## License

No explicit license has been added to this repository yet.

## Future Improvements

- Add real ESP32 sensor ingestion pipeline
- Improve dashboard analytics and crop recommendations
- Add alerts for water stress and disease risk
- Expand multilingual AI support
- Add historical trend charts and predictive forecasting
- Enhance user roles and farm management workflows

---

Built with a focus on smart farming, water efficiency, and AI-driven agricultural insights.
