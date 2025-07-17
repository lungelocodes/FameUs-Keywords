# Keyword Research Tool

## Overview

This is a full-stack keyword research application built with React, Express, and TypeScript. It provides SEO professionals with comprehensive keyword analysis, search volume data, and competitive intelligence through integration with DataForSEO API. The application features a modern, responsive UI built with shadcn/ui components and Tailwind CSS.

## User Preferences

Preferred communication style: Simple, everyday language.
UI Design: Performance-first, minimalistic, clean layout with plenty of white space, monochrome/low-saturation color palette with high-contrast text for readability, fast-loading lightweight components without heavy graphics or animations.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: shadcn/ui components with Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Data Layer**: Drizzle ORM with PostgreSQL (Neon Database)
- **API Integration**: DataForSEO REST API for keyword data
- **Session Management**: PostgreSQL-based session storage
- **Build**: ESBuild for server bundling

### Database Schema
- **keywords**: Stores keyword data including search volume, CPC, difficulty scores
- **serpResults**: SERP analysis data for keyword positioning
- **searchHistory**: User search history with filters and result counts

## Key Components

### Frontend Components
- **Dashboard**: Main application interface with keyword research tools
- **KeywordForm**: Search form with advanced filtering options
- **KeywordTable**: Sortable, filterable data table with export functionality
- **ApiStatus**: Real-time API connection monitoring
- **Sidebar**: Navigation and tool organization

### Backend Services
- **Storage Layer**: Abstracted storage interface with in-memory fallback
- **DataForSEO Integration**: API client for keyword and SERP data
- **Custom Scoring**: Proprietary keyword difficulty calculation algorithm

### Shared Resources
- **Schema Definitions**: Zod schemas for type-safe data validation
- **Type Safety**: Full TypeScript coverage across client and server

## Data Flow

1. **User Input**: Keywords entered through KeywordForm component
2. **API Request**: Frontend sends structured request to Express backend
3. **External API**: Backend queries DataForSEO API for keyword metrics
4. **Data Processing**: Custom algorithms calculate difficulty scores and analyze SERP features
5. **Database Storage**: Results stored in PostgreSQL with Drizzle ORM
6. **Response**: Processed data returned to frontend via React Query
7. **UI Update**: KeywordTable displays results with sorting and filtering
8. **Export**: CSV export functionality for data analysis

## External Dependencies

### Core APIs
- **DataForSEO API**: Primary data source for keyword metrics and SERP analysis
- **Neon Database**: PostgreSQL hosting with serverless architecture

### Key Libraries
- **UI Framework**: React with Radix UI components
- **Data Fetching**: TanStack Query for server state management
- **Validation**: Zod for runtime type checking
- **Styling**: Tailwind CSS with shadcn/ui design system
- **Database**: Drizzle ORM with PostgreSQL driver

### Development Tools
- **Replit Integration**: Development environment optimization
- **TypeScript**: Full type safety across the stack
- **Vite**: Fast development server and build tool

## Deployment Strategy

### Development
- **Local Development**: Vite dev server with Express backend
- **Hot Reload**: Both client and server support hot module replacement
- **Environment**: NODE_ENV-based configuration switching

### Production Build
- **Frontend**: Vite builds optimized React bundle to `dist/public`
- **Backend**: ESBuild creates single server bundle in `dist`
- **Static Serving**: Express serves built frontend assets
- **Database**: Drizzle migrations handle schema updates

### Environment Configuration
- **Database**: `DATABASE_URL` for PostgreSQL connection
- **API Keys**: `DATAFORSEO_LOGIN` and `DATAFORSEO_PASSWORD` for external API
- **Session**: PostgreSQL-backed session storage for user state

### Scaling Considerations
- **Database**: PostgreSQL with connection pooling via Neon
- **API Limits**: Rate limiting and caching for DataForSEO requests
- **State Management**: Server-side session storage for user preferences
- **Static Assets**: Vite optimizes and bundles all client resources