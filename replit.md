# AI Impact Tracker - Research Database

## Overview

A research aggregation tool that tracks AI environmental impact from academic sources (Google Scholar). The application enables researchers to search, import, and analyze papers about AI energy consumption and CO2 emissions.

## Features

- **Dashboard**: Overview with stats (total papers, models, metrics, citations)
- **Research Papers**: Searchable database with filtering by year, citations
- **Model Comparison**: Track and compare AI models' environmental metrics
- **Timeline**: Visualize research publication trends over time
- **Scholar Search**: Import papers from Google Scholar (mock integration)
- **Export**: Download data in CSV, JSON, or BibTeX format

## Tech Stack

- **Frontend**: React, TanStack Query, Wouter routing, Tailwind CSS, Shadcn UI
- **Backend**: Express.js, Drizzle ORM
- **Database**: PostgreSQL (Neon-backed)
- **Charts**: Recharts

## Project Structure

```
client/src/
├── components/     # Reusable UI components
│   ├── app-sidebar.tsx      # Main navigation sidebar
│   ├── paper-card.tsx       # Research paper display card
│   ├── model-table.tsx      # AI models comparison table
│   ├── stats-card.tsx       # Statistics display cards
│   ├── search-filters.tsx   # Filter controls
│   ├── timeline-chart.tsx   # Timeline visualization
│   ├── export-panel.tsx     # Export options panel
│   ├── empty-state.tsx      # Empty state displays
│   ├── loading-skeleton.tsx # Loading placeholders
│   ├── theme-provider.tsx   # Dark/light mode provider
│   └── theme-toggle.tsx     # Theme switcher
├── pages/
│   ├── dashboard.tsx        # Main dashboard
│   ├── papers.tsx           # Papers list
│   ├── paper-detail.tsx     # Individual paper view
│   ├── models.tsx           # Model comparison
│   ├── timeline.tsx         # Timeline view
│   ├── search.tsx           # Google Scholar search
│   └── export.tsx           # Data export
└── App.tsx                  # Main app with routing

server/
├── db.ts           # Database connection
├── storage.ts      # Data access layer (DatabaseStorage)
├── routes.ts       # API endpoints
└── index.ts        # Express server setup

shared/
└── schema.ts       # Drizzle schema & types
```

## Database Schema

- **research_papers**: Academic papers with title, authors, abstract, citations
- **ai_models**: AI models with energy/CO2 metrics
- **impact_metrics**: Extracted environmental impact data
- **scraping_jobs**: Scholar search tracking

## API Endpoints

- `GET /api/stats` - Dashboard statistics
- `GET /api/papers` - List papers (query params: search, year, minCitations)
- `POST /api/papers` - Create paper
- `GET /api/papers/:id` - Paper details with metrics
- `GET /api/models` - List AI models
- `POST /api/models` - Create model
- `GET /api/timeline` - Timeline data
- `GET /api/scholar/search?query=` - Mock Scholar search
- `GET /api/export/stats` - Export statistics

## Running the Application

```bash
npm run dev       # Start development server
npm run db:push   # Push database schema changes
```

## Design Guidelines

See `design_guidelines.md` for UI/UX standards including:
- Material Design with academic research refinements
- Typography: Inter for body, JetBrains Mono for metrics
- Sidebar navigation with filtering
- Data tables with sorting
- Timeline visualizations

## Recent Changes

- **2024-12-04**: Initial implementation
  - Full CRUD for papers, models, metrics
  - Mock Google Scholar search integration
  - Timeline visualization with Recharts
  - Export functionality (CSV, JSON, BibTeX)
  - Dark/light theme support
  - Responsive design with Shadcn sidebar
