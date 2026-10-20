# TraWell

An AI trip planner. You pick a destination, how many days, your budget and who you're travelling with, and TraWell asks Google's Gemini model to put together a day-by-day itinerary of places to visit. Trips are saved to your account so you can come back to them.

## Features

- Destination search with Google Places autocomplete
- Itinerary generation using the Gemini API
- Sign in with Auth0 (Google login)
- Trips saved per user in Firebase Firestore
- "My Trips" page to revisit saved itineraries
- Responsive UI with Tailwind CSS, shadcn/ui components and GSAP animations

## Tech stack

React 18, Vite, Tailwind CSS, Radix UI / shadcn, Gemini API, Google Maps Places API, Firebase Firestore, Auth0, React Router

## Getting started

```bash
git clone https://github.com/rohitbondala277/TraWell.git
cd TraWell
npm install
cp .env.example .env
```

Fill in `.env` with your own keys (see `.env.example` for the list), then:

```bash
npm run dev
```

You'll need:
- A Google Cloud project with the Places API enabled
- A Gemini API key from Google AI Studio
- An Auth0 application (Single Page App)
- A Firebase project with Firestore enabled

## Project structure

```
src/
  components/
    custom/        Header, Hero, Footer, Stats
    routes/        plan-a-trip, my-trips, all-trips
    ui/            shadcn components (button, card, dialog, input)
  Context/         login and ref contexts
  Service/         Gemini and Firebase setup
```

## What I'd improve

- Move the Gemini call to a small backend so the API key isn't exposed in the browser
- Add Firestore security rules so users can only read their own trips
- Add tests for the trip form validation
