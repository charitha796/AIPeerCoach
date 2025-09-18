# AI Peer Revision Coach

## Overview

AI Peer Revision Coach is a full-stack web application that helps students improve their writing through structured AI feedback, progress tracking, and interactive learning tools. The app supports multiple document types (essays, letters, reports, CVs, etc.) and provides detailed analysis using AI-powered text evaluation. Students can submit text directly or upload PDF/image files for automatic text extraction, receive comprehensive feedback with scores and suggestions, and track their progress over time.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript for type safety and modern component-based UI
- **Build Tool**: Vite for fast development and optimized production builds
- **Routing**: Wouter for lightweight client-side routing
- **UI Components**: Radix UI primitives with shadcn/ui component library for consistent, accessible design
- **Styling**: TailwindCSS with CSS variables for theming and responsive design
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Forms**: React Hook Form with Zod validation for robust form handling

### Backend Architecture
- **Runtime**: Node.js with Express.js for REST API endpoints
- **Language**: TypeScript throughout the stack for consistency and type safety
- **Storage Strategy**: Dual storage approach - in-memory storage for development/demo with PostgreSQL schema ready for production scaling
- **File Processing**: Multer for file uploads with memory storage, supporting PDF text extraction (pdf-parse) and OCR for images (Tesseract.js)
- **API Design**: RESTful endpoints with structured JSON responses and comprehensive error handling

### Data Storage
- **Development**: In-memory storage using Map-based implementation for rapid prototyping
- **Production Ready**: Drizzle ORM with PostgreSQL schema pre-configured for easy migration
- **Schema Design**: Two main entities - reviews (storing original text, AI responses, metadata) and user progress (tracking stats, badges, improvement metrics)
- **Data Persistence**: Local storage fallback on frontend for offline-first user experience

### AI Integration
- **Primary Provider**: Google Gemini 1.5 Flash API for cost-effective, high-quality text analysis
- **Response Structure**: Strict JSON schema validation ensuring consistent feedback format
- **Analysis Criteria**: Five-dimensional scoring (clarity, grammar, structure, tone, relevance) with detailed suggestions and improvements
- **Features**: Automated text improvement, line-by-line edits, quiz generation, and adaptive explanations

## External Dependencies

### AI Services
- **Google Gemini API**: Primary AI service for text analysis and feedback generation
- **Fallback Strategy**: Architecture supports easy integration of alternative LLM providers

### Database Services  
- **Neon Database**: PostgreSQL-compatible serverless database for production deployment
- **Drizzle Kit**: Database migrations and schema management

### File Processing
- **pdf-parse**: Server-side PDF text extraction
- **Tesseract.js**: Client-side OCR for image-based text extraction
- **Multer**: File upload middleware with configurable storage options

### UI and Styling
- **Radix UI**: Headless component primitives for accessibility and customization
- **Lucide Icons**: Consistent iconography throughout the application
- **TailwindCSS**: Utility-first styling with custom design system integration

### Development Tools
- **Vite Plugins**: Runtime error overlay, Replit integration, and development tooling
- **TypeScript**: Full-stack type safety with shared schema definitions
- **ESLint/Prettier**: Code quality and formatting standards