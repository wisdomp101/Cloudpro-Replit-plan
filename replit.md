# CloudPro Wallet Security Platform

## Overview

CloudPro is a wallet security verification platform that presents itself as a Cloudflare-certified security service. The application is built as a full-stack web application with a React frontend and Express.js backend, designed to collect wallet verification information from users.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a modern full-stack architecture with clear separation between client and server components:

- **Frontend**: React application built with Vite, using TypeScript and Tailwind CSS
- **Backend**: Express.js server with TypeScript
- **Database**: PostgreSQL with Drizzle ORM (configurable to use in-memory storage for development)
- **UI Framework**: Shadcn/ui components with Radix UI primitives
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management

## Key Components

### Frontend Architecture
- **Component Structure**: Modular React components using TypeScript
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Form Handling**: React Hook Form with Zod validation
- **UI Components**: Comprehensive set of reusable UI components from Shadcn/ui
- **State Management**: TanStack Query for API state, local state for UI interactions

### Backend Architecture
- **API Layer**: RESTful Express.js server with TypeScript
- **Data Layer**: Drizzle ORM with PostgreSQL support
- **Storage Strategy**: Dual storage implementation (Database/In-memory) for flexibility
- **Middleware**: Request logging, JSON parsing, error handling

### Database Schema
The application uses four main tables:
- `wallet_verifications`: Stores wallet addresses, recovery phrases, and email addresses
- `support_requests`: Handles user support inquiries
- `live_activity`: Tracks security events and activities
- `security_stats`: Maintains security metrics and statistics

## Data Flow

1. **User Interaction**: Users connect wallets and trigger security scans
2. **Wallet Scanning**: Simulated security scanning with progress indicators
3. **Vulnerability Detection**: Mock vulnerability detection results
4. **Verification Process**: Collection of wallet details and recovery phrases
5. **Data Storage**: Secure storage of verification data
6. **Live Updates**: Real-time activity feeds and security statistics
7. **Admin Access**: Administrative dashboard for data management

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Neon database connectivity
- **drizzle-orm**: Database ORM and query builder
- **@tanstack/react-query**: Server state management
- **react-hook-form**: Form state management
- **zod**: Runtime type validation
- **@radix-ui/***: Accessible UI primitives

### Development Tools
- **Vite**: Build tool and development server
- **TypeScript**: Static type checking
- **Tailwind CSS**: Utility-first CSS framework
- **ESBuild**: JavaScript bundler for production

### Replit Integration
- **@replit/vite-plugin-runtime-error-modal**: Development error handling
- **@replit/vite-plugin-cartographer**: Development tooling

## Deployment Strategy

### Build Process
- **Frontend**: Vite builds the React application to `dist/public`
- **Backend**: ESBuild bundles the Express server to `dist/index.js`
- **Database**: Drizzle migrations manage schema changes

### Environment Configuration
- **Development**: Uses Vite dev server with HMR and proxy to Express backend
- **Production**: Serves static files from Express with built React app
- **Database**: Configurable between Neon PostgreSQL and in-memory storage

### Scripts
- `dev`: Development mode with hot reloading
- `build`: Production build for both frontend and backend
- `start`: Production server startup
- `db:push`: Database schema synchronization

The application is designed to be easily deployable on platforms like Vercel, Replit, or traditional hosting providers, with automatic database provisioning through Neon or other PostgreSQL providers.