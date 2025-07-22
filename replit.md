# LIT Fire & Plumbing (Pvt) (Ltd) - Professional Fire Safety & Plumbing Services Website

## Overview

This is a professional fire safety and plumbing services website built for LIT Fire & Plumbing (Pvt) (Ltd). The application features a modern single-page application (SPA) architecture with a React frontend and Express.js backend, designed to showcase comprehensive fire safety and plumbing solutions for residential and commercial clients.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight client-side routing)
- **UI Framework**: Shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom fire safety brand colors
- **State Management**: TanStack Query (React Query) for server state
- **Form Handling**: React Hook Form with Zod validation
- **Build Tool**: Vite with React plugin

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **API Style**: RESTful API endpoints
- **Request Handling**: JSON parsing with express middleware
- **Logging**: Custom request/response logging middleware

### Data Storage Solutions
- **Database**: PostgreSQL (configured via Drizzle)
- **ORM**: Drizzle ORM with type-safe schema definitions
- **Connection**: Neon Database serverless PostgreSQL
- **Fallback**: In-memory storage implementation for development
- **Migrations**: Drizzle Kit for database schema management

### Authentication and Authorization
- **Current State**: No authentication system implemented
- **Session Management**: Basic session setup prepared (connect-pg-simple)
- **Access Control**: Open contact form submission, admin endpoints available

## Key Components

### Frontend Components
- **Header**: Centered logo design with company name below, navigation menu centered underneath, includes scroll progress indicator
- **Hero**: Interactive slideshow with parallax scrolling effects, auto-advancing slides, navigation arrows, slide indicators, and smooth animations
- **About**: Company information with scroll-triggered fade-in animations, hover effects on statistics cards, and floating certification badge
- **Why Choose Us**: Animated section with staggered card animations, floating icons, hover lift effects, and pulsing statistics bar
- **Services**: Six service cards with scale-in animations, image hover zoom, staggered reveals, and interactive hover states
- **Contact**: Contact form with validation and submission handling (animations ready for implementation)
- **Footer**: Company links and social media integration

### Backend Components
- **Routes**: Contact form submission and retrieval endpoints
- **Storage**: Abstracted storage interface with memory and database implementations
- **Schema**: Drizzle schema definitions for users and contact submissions
- **Validation**: Zod schemas for type-safe data validation

### UI System
- **Component Library**: Comprehensive Shadcn/ui component set
- **Design System**: Green and yellow themed color palette (lit-green, lit-yellow, lit-dark-green)
- **Animation System**: Custom CSS animations with intersection observer triggers, parallax effects, staggered reveals
- **Responsive Design**: Mobile-first approach with Tailwind breakpoints
- **Accessibility**: Radix UI primitives ensure ARIA compliance

### UX Enhancements & Animations
- **Scroll Progress Bar**: Real-time visual progress indicator in header
- **Parallax Scrolling**: Hero background moves at different speeds for depth effect
- **Intersection Animations**: Elements animate in when they enter viewport
- **Staggered Reveals**: Sequential animations for card grids and lists
- **Hover Effects**: Interactive lift, scale, and glow effects on interactive elements
- **Smooth Transitions**: Enhanced hover states with duration controls
- **Floating Elements**: Subtle continuous animations for visual interest
- **Image Zoom**: Service card images scale on hover for engagement

## Data Flow

### Contact Form Submission
1. User fills out contact form with personal and inquiry details
2. React Hook Form validates input using Zod schema
3. Form data submitted via TanStack Query mutation
4. Express backend validates and stores submission
5. Success/error feedback displayed via toast notifications
6. Form resets on successful submission

### Page Navigation
1. Header navigation uses smooth scrolling to page sections
2. Wouter handles client-side routing for different pages
3. 404 page displayed for undefined routes

### Data Persistence
1. Contact submissions stored in PostgreSQL via Drizzle ORM
2. Memory storage used as fallback during development
3. Database connection managed through environment variables

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL hosting
- **Connection**: Via DATABASE_URL environment variable
- **Driver**: @neondatabase/serverless for edge compatibility

### UI and Styling
- **Fonts**: Inter font family from Google Fonts
- **Icons**: Lucide React icon library
- **Images**: Unsplash for professional fire safety imagery
- **Logo**: Custom fire safety consulting branding

### Development Tools
- **Replit Integration**: Custom plugins for development environment
- **Error Handling**: Runtime error overlay for development
- **Code Mapping**: Source map support for debugging

### Analytics and Monitoring
- **Development Banner**: Replit development environment indicator
- **Request Logging**: Custom middleware for API request tracking

## Deployment Strategy

### Build Process
1. **Frontend**: Vite builds React application to `dist/public`
2. **Backend**: ESBuild bundles server code to `dist/index.js`
3. **Assets**: Static files served from build directory
4. **Environment**: NODE_ENV determines development vs production mode

### Development Workflow
1. **Database Setup**: `npm run db:push` applies schema changes
2. **Development Server**: `npm run dev` starts both frontend and backend
3. **Type Checking**: `npm run check` validates TypeScript
4. **Hot Reload**: Vite HMR for frontend, tsx for backend restart

### Production Deployment
1. **Build**: `npm run build` creates production bundles
2. **Start**: `npm start` runs production server
3. **Static Serving**: Express serves built React application
4. **API Routes**: Backend endpoints handle form submissions and data retrieval

### Environment Configuration
- **Database**: Requires DATABASE_URL for PostgreSQL connection
- **Development**: Local development with memory storage fallback
- **Production**: Full PostgreSQL integration with session management