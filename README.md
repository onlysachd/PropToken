# Real Estate Tokenization Platform

A modern real estate fractional ownership platform built with React, Node.js, and PostgreSQL. This application enables users to invest in premium properties through tokenized ownership with support for KYC verification, wallet integration, and secure transactions.

## 🏗️ Architecture

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development and optimized builds
- **Tailwind CSS** with shadcn/ui components
- **TanStack React Query** for server state management
- **Wouter** for lightweight routing

### Backend
- **Node.js** with Express.js
- **PostgreSQL** with Drizzle ORM
- **Replit Auth** with OpenID Connect
- **Session management** with PostgreSQL storage

### Database
- **PostgreSQL** with Drizzle ORM
- **Type-safe** database operations
- **Automatic migrations** with `npm run db:push`

## 🚀 Features

- **User Authentication** - Secure login with Replit Auth
- **Property Browsing** - Comprehensive property catalog with filtering
- **Tokenized Investment** - Fractional ownership through token purchases
- **Portfolio Management** - Real-time tracking and performance metrics
- **KYC Verification** - Multi-step compliance workflow
- **Wallet Integration** - Web3 wallet connectivity support
- **Transaction History** - Complete audit trail of investments
- **Multi-City Coverage** - Properties across Mumbai, Delhi NCR, Bangalore, Hyderabad, Pune, and Chennai

## 📋 Prerequisites

- Node.js 18 or higher
- PostgreSQL database
- Environment variables (see below)

## 🛠️ Installation

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd real-estate-tokenization
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
Create a `.env` file with:
```env
DATABASE_URL=your_postgresql_connection_string
SESSION_SECRET=your_session_secret_key
REPL_ID=your_replit_app_id
ISSUER_URL=https://replit.com/oidc
REPLIT_DOMAINS=your_domain.replit.app
```

4. **Set up the database**
```bash
npm run db:push
```

5. **Start the development server**
```bash
npm run dev
```

The application will be available at `http://localhost:5000`

## 🏙️ Sample Data

The platform includes sample properties across major Indian cities:

- **Mumbai**: Luxury apartments, commercial complexes, retail spaces
- **Delhi NCR**: Residential towers, IT parks, warehouses
- **Bangalore**: Tech parks, villa projects, hotels
- **Hyderabad**: Office complexes, gated communities
- **Pune**: Business parks, residential complexes
- **Chennai**: IT campuses, beachside resorts, apartment complexes

## 📁 Project Structure

```
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom React hooks
│   │   └── lib/            # Utility functions
├── server/                 # Express backend
│   ├── db.ts              # Database connection
│   ├── routes.ts          # API routes
│   ├── storage.ts         # Data access layer
│   └── replitAuth.ts      # Authentication setup
├── shared/                 # Shared types and schemas
│   └── schema.ts          # Drizzle database schema
└── components.json        # shadcn/ui configuration
```

## 🔒 Security Features

- **Secure Authentication** with OpenID Connect
- **Session Management** with HTTP-only cookies
- **SQL Injection Protection** with parameterized queries
- **CORS Configuration** for domain restrictions
- **Environment Variable Protection** for sensitive data

## 📊 Database Schema

Key entities:
- **Users** - User authentication and profile data
- **Properties** - Real estate property information
- **Investments** - User investment records
- **Transactions** - Financial transaction history
- **KYC Verifications** - Compliance verification data
- **Earnings** - Investment returns and distributions

## 🚀 Deployment

This project is optimized for deployment on Replit but can be deployed to any platform supporting Node.js:

1. **Replit** - Direct deployment with integrated database
2. **Vercel/Netlify** - Frontend deployment with serverless functions
3. **Heroku/Railway** - Full-stack deployment
4. **AWS/GCP** - Enterprise deployment with managed databases

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License.

## 🆘 Support

For support and questions:
- Create an issue in the GitHub repository
- Contact the development team

---

Built with ❤️ for the future of real estate investment