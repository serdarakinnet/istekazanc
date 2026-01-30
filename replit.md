# İşte Kazanç - Financial Literacy Platform

## Overview
İşte Kazanç is a Turkish financial literacy platform that leverages AI-powered stock market analysis to help users improve their financial knowledge. It provides stock ratings, detailed analyses, and investment insights through an intuitive web interface. The platform aims to educate and empower users for informed investment decisions. Authenticated users have unlimited free access to analyses and can save favorites. Admin and Pro members can create new analyses. A key feature is the comprehensive BES (Individual Retirement System) calculator for financial simulations.

## User Preferences
Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18+ with TypeScript, built with Vite.
- **UI Component System**: Radix UI primitives with shadcn/ui (New York style variant), offering accessible components and customizable styling.
- **Styling**: Tailwind CSS with a custom configuration, optimized for financial data and supporting dark/light mode. Typography uses Inter and JetBrains Mono.
- **State Management**: TanStack Query for server state and caching; React hooks for local component state.
- **Routing**: Wouter for lightweight client-side routing.
- **File Upload**: Native HTML file inputs for temporary uploads (Excel, PNGs), stored in `/tmp` during analysis.

### Backend Architecture
- **Server Framework**: Express.js with Node.js and TypeScript (ESM).
- **Development Setup**: Custom Vite integration for HMR and SSR-style HTML.
- **API Design**: RESTful endpoints covering authentication, analyses, favorites, and admin functions (e.g., file upload, analysis creation, settings management).
- **Authentication**: Replit Auth (OpenID Connect) integrated with Passport.js and express-session, using PostgreSQL for session storage. Protected routes use `isAuthenticated` middleware.
- **AI Integration**: OpenAI GPT-4o-mini with vision capabilities for multi-modal analysis.
    - **Pipeline**: Temporary files are converted (Excel to CSV, PNGs to Base64) and sent to AI.
    - **Analysis Framework**: Covers Fundamental, Technical, and Trading Analysis, generating comprehensive reports.
    - **Output**: AI returns company name, a 1-100 rating, and a detailed Turkish analysis.
- **Error Handling**: Robust error handling ensures temporary files are always cleaned up and provides user-friendly messages.

### Database Architecture
- **ORM**: Drizzle ORM for type-safe schema definitions and migrations.
- **Schema Design**: Includes tables for `users`, `analyses`, `favorites`, and `sessions`.
- **Access Control**:
    - All authenticated users: Unlimited viewing.
    - Admin user: Full system access, user management, and analysis creation.
    - Pro members: Can create analyses.
    - Premium subscription features are disabled; all users get unlimited access.

## External Dependencies
- **Database**: PostgreSQL via Neon serverless driver.
- **AI Service**: OpenAI GPT-4o-mini for AI-powered analysis.
- **Temporary File Storage**: Server's `/tmp/uploads` directory for Excel spreadsheets and PNG images, with automated cleanup.
- **Authentication Provider**: Replit OpenID Connect service.
- **CDN**: Google Fonts for typography.