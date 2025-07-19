# Real Estate Investment Platform

## Overview

This is a modern real estate fractional ownership platform built with React frontend and Node.js/Express backend. The application enables users to invest in premium properties through tokenized ownership, with support for KYC verification, wallet integration, and secure transactions. The platform is designed for the Indian market with INR-based transactions and compliance-ready features.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: Radix UI components with Tailwind CSS styling (shadcn/ui design system)
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack React Query for server state management
- **Styling**: Tailwind CSS with CSS variables for theming

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js for RESTful API endpoints
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Authentication**: Replit Auth integration with OpenID Connect
- **Session Management**: Express sessions with PostgreSQL storage

### Database Design
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema Location**: Shared between frontend and backend in `/shared/schema.ts`
- **Primary Entities**: Users, Properties, Investments, KYC Verifications, Earnings, Transactions
- **Secondary Market Entities**: Market Orders, Trades, Liquidity Pools, Liquidity Positions, Price History, Compliance Records
- **Session Storage**: Dedicated sessions table for authentication state
- **Trading Infrastructure**: Complete order book, trade execution, and compliance tracking tables

## Key Components

### Authentication System
- **Provider**: Replit Auth with OIDC integration
- **Session Storage**: PostgreSQL-backed sessions with configurable TTL
- **Security**: HTTP-only cookies with secure flags for production
- **User Management**: Automatic user creation/updates on authentication

### Property Management
- **Property Listing**: Complete property catalog with filtering capabilities
- **Tokenization**: Each property divided into purchasable tokens
- **Investment Tracking**: User investment portfolios with real-time updates
- **Property Types**: Support for residential, commercial, industrial, hotel, vacation, and retail properties

### KYC Verification
- **Multi-step Process**: Progressive KYC form with document uploads
- **Status Tracking**: Pending, approved, rejected states with admin review
- **Compliance**: India-specific KYC requirements (PAN, Aadhaar)
- **Document Management**: Secure document storage and verification workflow

### Investment Engine
- **Token Purchase**: Fractional ownership through token purchases
- **Portfolio Management**: Real-time portfolio tracking and performance metrics
- **Transaction History**: Complete audit trail of all investment activities
- **Earnings Distribution**: Automated earnings calculations and distributions

### Secondary Market Infrastructure
- **Order Book System**: Complete buy/sell order management with automatic matching
- **Trading Engine**: Real-time trade execution with compliance checks and AML screening
- **Liquidity Pools**: Automated market maker functionality for token liquidity
- **Price Discovery**: Real-time price tracking with historical data and market statistics
- **Compliance Framework**: KYC verification, trading eligibility, and regulatory compliance
- **Market Data APIs**: Complete market statistics, volume tracking, and price history

### Wallet Integration
- **Multi-wallet Support**: MetaMask and other Web3 wallet connections
- **Address Management**: Secure wallet address storage and verification
- **Transaction Integration**: Blockchain transaction support (prepared for future implementation)

## Data Flow

### Authentication Flow
1. User initiates login through Replit Auth
2. OIDC provider validates credentials
3. Session created in PostgreSQL with user data
4. Frontend receives authentication state
5. Subsequent requests include session cookies

### Investment Flow
1. User browses properties with real-time availability
2. KYC verification required before investment
3. Investment modal for token selection and payment
4. Transaction recorded in database
5. Portfolio updated with new investment
6. Real-time UI updates across components

### Data Synchronization
- **Optimistic Updates**: Immediate UI feedback with server confirmation
- **Cache Invalidation**: Strategic query invalidation on mutations
- **Real-time Updates**: Automatic refresh of critical data (portfolio, availability)

## External Dependencies

### Database & Infrastructure
- **Database**: Neon PostgreSQL (serverless PostgreSQL)
- **Connection Pooling**: Neon serverless driver with WebSocket support
- **Environment**: Replit-hosted with integrated development tools

### UI & Styling
- **Component Library**: Radix UI primitives for accessibility
- **Styling**: Tailwind CSS with custom design tokens
- **Icons**: Lucide React for consistent iconography
- **Fonts**: System fonts with web fallbacks

### Development Tools
- **TypeScript**: Full type safety across frontend and backend
- **ESLint**: Code quality and consistency
- **PostCSS**: CSS processing with Tailwind and Autoprefixer
- **Vite Plugins**: Runtime error overlay and development tools

### Authentication & Security
- **Replit Auth**: Integrated authentication provider
- **Session Security**: Secure cookie configuration
- **CORS**: Configured for Replit domain restrictions
- **Environment Variables**: Secure configuration management

## Deployment Strategy

### Development Environment
- **Platform**: Replit with integrated IDE and hosting
- **Hot Reload**: Vite dev server with instant updates
- **Database**: Neon PostgreSQL with automatic provisioning
- **Environment**: Automatic environment variable management

### Production Build
- **Frontend**: Vite production build with optimization
- **Backend**: ESBuild compilation for Node.js deployment
- **Assets**: Static asset serving through Express
- **Database**: Production PostgreSQL with migration support

### Monitoring & Logging
- **Request Logging**: Structured API request/response logging
- **Error Handling**: Centralized error handling with user-friendly messages
- **Performance**: Built-in Vite performance monitoring
- **Database**: Drizzle query logging in development

### Security Considerations
- **Authentication**: OIDC-compliant authentication flow
- **Session Management**: Secure session storage with TTL
- **Database**: Parameterized queries preventing SQL injection
- **CORS**: Restricted to authorized domains
- **Environment**: Secure environment variable handling

The architecture is designed for scalability and compliance with financial regulations, with clear separation of concerns and robust error handling throughout the application stack.