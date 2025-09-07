# 🎮 Gamified Event Platform

<div align="center">

[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Prisma](https://img.shields.io/badge/Prisma-5.0-2D3748?style=for-the-badge&logo=prisma)](https://prisma.io/)
[![WebSockets](https://img.shields.io/badge/WebSockets-Socket.IO-010101?style=for-the-badge&logo=socket.io)](https://socket.io/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker)](https://docker.com/)

**A comprehensive gamified event engagement platform with real-time features, QR/NFC scanning, live leaderboards, and rewards system. Built for Unity integration and enterprise-scale events.**

[🚀 Live Demo](#) • [📖 Documentation](#) • [🐛 Report Bug](../../issues) • [✨ Request Feature](../../issues)

</div>

## 🚀 Features

### Core Platform
- **Multi-tenant Architecture** - Organizations and events management
- **User Authentication** - Email magic links + OAuth (Google, GitHub)
- **Role-Based Access Control** - 4 roles with 25+ granular permissions
- **Event Management** - Complete CRUD with registration system

### Scanning & Points System
- **Dual Scanning Methods** - QR codes (html5-qrcode) + NFC (Web NFC API for Android)
- **Anti-Fraud System** - 5-layer validation with risk scoring
- **Rate Limiting** - Multi-tier protection (global/event/checkpoint)
- **Real-time Points** - Redis-cached leaderboards with instant updates
- **Transaction Ledger** - Complete audit trail for all point activities

### Analytics & Admin Tools
- **Comprehensive Analytics** - Real-time charts and reports
- **Admin Dashboard** - Full event and user management
- **QR/NFC Generation** - Bulk generation with ZIP downloads
- **Location Management** - Checkpoint mapping and spatial data

## 🛠️ Tech Stack

- **Framework:** Next.js 15 with App Router + TypeScript
- **Database:** PostgreSQL with Prisma ORM
- **Caching:** Redis for sessions and rate limiting
- **Authentication:** NextAuth.js
- **UI:** Tailwind CSS + Shadcn UI + Radix primitives
- **Charts:** Recharts for analytics
- **QR/NFC:** html5-qrcode + Web NFC API
- **Validation:** Zod
- **Code Quality:** ESLint + Prettier + Husky

## 📦 Installation

1. **Clone the repository**
```bash
git clone https://github.com/beef888/event-platform-2024.git
cd event-platform-2024
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up environment variables**
```bash
cp .env.example .env.local
```

Edit `.env.local` with your configuration:
```env
# Database
DATABASE_URL="postgresql://user:password@localhost:5432/instamedia"

# Redis
REDIS_URL="redis://localhost:6379"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key"

# OAuth Providers (optional)
GOOGLE_CLIENT_ID="your-google-client-id"
GOOGLE_CLIENT_SECRET="your-google-client-secret"
GITHUB_ID="your-github-client-id"
GITHUB_SECRET="your-github-client-secret"

# Email (for magic links)
EMAIL_SERVER="smtp://user:password@smtp.example.com:587"
EMAIL_FROM="noreply@yourapp.com"
```

4. **Set up the database**
```bash
npm run db:generate
npm run db:push
npm run db:seed
```

5. **Start the development server**
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 🚢 Deployment

### Vercel (Recommended)

1. **Deploy to Vercel**
```bash
npm i -g vercel
vercel
```

2. **Set up environment variables** in Vercel dashboard

3. **Set up external services:**
   - PostgreSQL database (Vercel Postgres, Supabase, or similar)
   - Redis instance (Upstash, Redis Cloud, or similar)

### Docker

```bash
# Development
npm run docker:dev

# Production
docker-compose up -d
```

## 📊 Database Schema

The platform uses a comprehensive schema with 15 entities:

- **Users & Authentication** - User, Account, Session, VerificationToken
- **Organizations & Events** - Organization, Event, EventRegistration, EventRole
- **Scanning System** - Checkpoint, Scan
- **Gamification** - Badge, UserBadge, PointsLedger, UserEventStats
- **Content & Rewards** - EventContent, Reward, Redemption, AuditLog

## 🔧 API Endpoints

### Public APIs
- `GET /api/events` - List public events
- `POST /api/scan` - Process QR/NFC scans
- `GET /api/users/me/*` - User profile and statistics

### Admin APIs
- `/api/admin/events/*` - Event management
- `/api/admin/events/[id]/checkpoints/*` - Checkpoint management
- `/api/admin/events/[id]/analytics/*` - Analytics and reports

## 🎯 Usage

### For Event Organizers
1. **Create Organization** and invite team members
2. **Set up Events** with dates, venue, and branding
3. **Create Checkpoints** with QR/NFC codes and point values
4. **Generate QR Codes** for printing or digital display
5. **Monitor Analytics** in real-time dashboard

### For Attendees
1. **Register for Events** via public event pages
2. **Scan QR/NFC codes** at checkpoints to earn points
3. **View Leaderboards** and track progress
4. **Earn Badges** and redeem rewards
5. **Check Statistics** and scan history

## 🔒 Security Features

- **Multi-layer Fraud Detection** - Device fingerprinting, location validation, behavior analysis
- **Rate Limiting** - Prevents abuse with Redis-based limits
- **RBAC Authorization** - Granular permissions system
- **Audit Logging** - Complete activity tracking
- **Session Management** - Secure JWT with rotation

## 🧪 Testing

```bash
# Run tests
npm test

# Type checking
npm run type-check

# Linting
npm run lint

# Code formatting
npm run format
```

## 📱 Unity Integration

The platform is designed to work with Unity game stations:

- **WebSocket Support** - Real-time communication ready
- **JSON APIs** - Easy integration with Unity's HTTP clients
- **QR/NFC Data** - Standardized data formats for Unity parsing

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For issues and questions:
- Create an issue in the GitHub repository
- Check the documentation
- Contact the development team

---

Built with ❤️ for engaging event experiences