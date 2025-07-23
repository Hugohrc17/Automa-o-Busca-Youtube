# YouTube Gaming Lead Capture System

## Overview

This is a full-stack web application designed to help find and manage YouTube gaming channels for video editing services. The system allows users to search for gaming channels, manage contact information, track outreach efforts, and export data for business development purposes.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modern full-stack architecture with clear separation between client and server components:

- **Frontend**: React-based single-page application with TypeScript
- **Backend**: Express.js REST API with WebSocket support for real-time updates
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Build System**: Vite for frontend bundling and development server
- **Styling**: Tailwind CSS with shadcn/ui component library

## Key Components

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **UI Components**: shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **Real-time Updates**: WebSocket client for live search progress updates

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database Layer**: Drizzle ORM with PostgreSQL
- **Real-time Communication**: WebSocket server for broadcasting search updates
- **Web Scraping**: Puppeteer for YouTube channel data extraction
- **Database Provider**: Neon serverless PostgreSQL

### Database Schema
The system uses two main entities:
- **Channels**: Stores YouTube channel information including name, subscriber count, niche, contact info, and outreach status
- **Search Jobs**: Tracks search operations with progress, keywords, and results

## Data Flow

1. **Search Initiation**: Users configure search parameters (keywords, subscriber range, result limits)
2. **Web Scraping**: Backend uses Puppeteer to scrape YouTube for matching channels
3. **Real-time Updates**: WebSocket broadcasts search progress to connected clients
4. **Data Storage**: Found channels are stored in PostgreSQL with deduplication
5. **Channel Management**: Users can view, filter, and update contact status of channels
6. **Data Export**: System provides export functionality for business use

## External Dependencies

### Core Dependencies
- **Database**: Neon PostgreSQL serverless database
- **Web Scraping**: Puppeteer for headless browser automation
- **UI Components**: Radix UI primitives and shadcn/ui components
- **State Management**: TanStack Query for API state management
- **Validation**: Zod for runtime type validation with Drizzle integration

### Development Tools
- **Build**: Vite with React plugin and error overlay
- **Database Migrations**: Drizzle Kit for schema management
- **TypeScript**: Full type safety across frontend and backend
- **Linting/Formatting**: Configured for TypeScript and React

## Deployment Strategy

The application is designed for deployment on Replit with the following characteristics:

- **Development**: Uses Vite dev server with HMR and error overlays
- **Production**: Builds to static assets served by Express
- **Database**: Configured for Neon PostgreSQL with connection pooling
- **Environment**: Uses environment variables for database connection
- **Build Process**: Single command builds both frontend and backend
- **Serving**: Express serves both API routes and static frontend assets

The architecture supports easy scaling and modification, with clear separation of concerns between data scraping, storage, and presentation layers.