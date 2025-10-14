# ATL Cheap Flights 🛫

Flight deal alerts for Atlanta travelers. Real deals, local focus, no hype.

**Website:** (Coming soon)  
**Newsletter:** ATL Cheap Flights via Beehiiv  
**Status:** 🔨 In Development (Phase 2)

---

## 📋 Project Overview

ATL Cheap Flights is a flight deal alert service built exclusively for Atlanta (ATL) travelers. We monitor prices on 500+ daily routes, detect deals with 50%+ savings, and send curated alerts via email. Unlike generic platforms, we focus on real value and authentic ATL culture.

### Key Features
- ✈️ **ATL-Only Focus**: All flights depart from Hartsfield-Jackson Atlanta International Airport
- 💰 **Real Deals**: Only 50%+ savings flagged as deals
- 🔔 **Instant Alerts**: Beehiiv email notifications within minutes of price drops
- 🎫 **Mistake Fares**: Premium subscribers get ultra-rare pricing errors
- 🌍 **All Destinations**: Domestic & International routes from ATL
- 🎨 **Local Branding**: Rooted in Atlanta's transit heritage and culture

### Tech Stack
```
Frontend:    Next.js + React + Tailwind CSS
Backend:     Node.js + Express (or Next.js API Routes)
Database:    PostgreSQL (Vercel Postgres or Supabase)
Email:       Beehiiv API
Payments:    Stripe (via Beehiiv)
Flight Data: Amadeus API
Deployment:  Vercel
```

---

## 🚀 Current Status

### Phase 1: Setup ✅ IN PROGRESS
- [x] GitHub repository created
- [x] Beehiiv publication configured (Email templates, tiers, Stripe integration)
- [ ] Vercel deployment setup
- [ ] PostgreSQL database created
- [ ] Amadeus API access

### Phase 2: Development 🔨 NEXT
- [ ] Deal detection algorithm
- [ ] Flight monitoring service (cron job)
- [ ] Beehiiv API integration
- [ ] Website frontend
- [ ] Brand design implementation

### Phase 3: Testing (Upcoming)
- [ ] Email campaign testing
- [ ] Beta user testing (10 ATL travelers)
- [ ] Performance optimization

### Phase 4: Launch (Upcoming)
- [ ] Public website deployment
- [ ] SEO & analytics setup

### Phase 5: Growth (Upcoming)
- [ ] Marketing campaigns
- [ ] Referral program
- [ ] Community building

**View full project timeline:** [GitHub Projects Board](LINK_TO_BOARD)

---

## 📁 Project Structure

```
atl-cheap-flights/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── feature.md
│   │   ├── blocker.md
│   │   └── bug.md
│   └── workflows/
│       └── ci.yml
│
├── docs/
│   ├── BEEHIIV_SETUP.md          ← Email service setup
│   ├── IMPLEMENTATION.md          ← Architecture docs
│   ├── CONTENT_STRATEGY.md        ← Marketing & content
│   └── API_REFERENCE.md           ← API documentation
│
├── src/
│   ├── backend/
│   │   ├── api/
│   │   │   ├── subscribe.js       ← Subscribe endpoint
│   │   │   ├── webhooks.js        ← Beehiiv webhooks
│   │   │   └── deals.js           ← Deal endpoints
│   │   ├── services/
│   │   │   ├── amadeus.js         ← Flight API client
│   │   │   ├── beehiiv.js         ← Email service
│   │   │   ├── dealDetection.js   ← Deal algorithms
│   │   │   └── database.js        ← DB queries
│   │   └── jobs/
│   │       └── monitorFlights.js  ← Cron job
│   │
│   └── frontend/
│       ├── pages/
│       │   ├── index.jsx          ← Home page
│       │   ├── pricing.jsx        ← Pricing page
│       │   └── api/
│       │       └── subscribe.js   ← Next.js API route
│       ├── components/
│       │   ├── DealCard.jsx
│       │   ├── SignupForm.jsx
│       │   ├── PricingModal.jsx
│       │   └── Header.jsx
│       └── styles/
│           └── globals.css
│
├── .env.example                    ← Environment template
├── .env.local                      ← LOCAL ONLY (never commit!)
├── README.md                       ← This file
├── package.json
├── next.config.js
└── vercel.json
```

---

## 🔐 Environment Variables

**Never commit `.env.local` to GitHub!**

Copy `.env.example` to `.env.local` and fill in your keys:

```bash
cp .env.example .env.local
```

Required variables:

```env
# Beehiiv Email Service
BEEHIIV_API_KEY=your_api_key
BEEHIIV_PUBLICATION_ID=your_pub_id
BEEHIIV_WEBHOOK_SECRET=your_webhook_secret

# Stripe Payment Processing
STRIPE_PUBLIC_KEY=pk_test_...
STRIPE_SECRET_KEY=sk_test_...

# Amadeus Flight API
AMADEUS_CLIENT_ID=your_client_id
AMADEUS_CLIENT_SECRET=your_client_secret

# Database
DATABASE_URL=postgresql://...

# Environment
NODE_ENV=development
NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

---

## 💻 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn
- PostgreSQL (local or remote)
- Beehiiv account
- Amadeus API access

### Installation

```bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/atl-cheap-flights.git
cd atl-cheap-flights

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your API keys

# Run database migrations
npm run db:migrate

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the website.

### Development Commands

```bash
# Run development server
npm run dev

# Run tests
npm test

# Run deal monitoring service (local)
npm run monitor

# Build for production
npm run build

# Start production server
npm start
```

---

## 📦 Dependencies

### Core
- `next`: React framework
- `react`: UI library
- `tailwindcss`: Styling
- `axios`: HTTP client

### Backend Services
- `node-cron`: Scheduled jobs
- `pg`: PostgreSQL client
- `dotenv`: Environment variables

### Email & Payments
- `axios`: For Beehiiv API calls
- (Stripe handled via Beehiiv)

### Development
- `eslint`: Code quality
- `jest`: Testing

See `package.json` for full dependency list.

---

## 🔗 API Integration

### Beehiiv
- **Docs**: beehiiv.com/docs
- **API Key**: Store in `BEEHIIV_API_KEY`
- **Publication ID**: Store in `BEEHIIV_PUBLICATION_ID`

Main endpoints used:
- `POST /v2/subscriptions` - Add subscriber
- `POST /v2/posts` - Send campaign
- Webhooks - Subscription events

### Amadeus
- **Docs**: developers.amadeus.com
- **Keys**: Store in `AMADEUS_CLIENT_ID` & `AMADEUS_CLIENT_SECRET`

Main endpoints used:
- `/v2/shopping/flight-offers` - Search flights
- `/v2/analytics/fare-search-history` - Historical prices

### Google Flights
- Deep links generated dynamically
- Format: `https://www.google.com/travel/flights?q=...`
- No API key needed

---

## 📊 GitHub Project Board

Track progress and blockers using our GitHub Project Board:

**View Board**: [GitHub Projects - ATL Cheap Flights](LINK_TO_BOARD)

Columns:
- 📋 **Backlog**: Future work
- 🔵 **In Progress**: Currently being worked on
- 🟡 **Blocked**: Waiting on something
- ✅ **Done**: Completed

To move an issue:
1. Go to GitHub Issues
2. Create/update issue with current status
3. Project board auto-updates

---

## 📝 Contributing

We're in early development. Contributions welcome!

### To Report a Bug
1. Check existing issues
2. Create issue using `bug.md` template
3. Include steps to reproduce

### To Request a Feature
1. Check existing issues
2. Create issue using `feature.md` template
3. Link to related issues with `depends on` or `blocks`

### To Submit Code
1. Create a feature branch: `git checkout -b feature/your-feature`
2. Make changes
3. Test locally: `npm test`
4. Commit with clear message: `git commit -m "Add feature: description"`
5. Push: `git push origin feature/your-feature`
6. Open Pull Request

---

## 🎨 Brand Guidelines

ATL Cheap Flights has a distinctive visual identity rooted in Atlanta's aviation heritage.

### Colors
- **Chiefs Blue** `#042576` - Primary, trust, sky
- **Eastern Light Blue** `#78ADD1` - Accent, lightness
- **Chiefs Red** `#B01534` - CTAs, urgency, deals

### Typography
- **Headers** (Lobster Two): Retro, playful ATL spirit
- **Body** (Noto Sans): Clean, readable, modern
- **CTAs** (Futura Bold): Bold, confident, urgent

### Tone
- Local, authentic, proud of ATL
- Witty and energetic
- Direct and helpful
- Never generic or corporate

For full brand guidelines, see `docs/BRAND.md`

---

## 📈 Analytics & Monitoring

### Metrics We Track
- Subscriber count (Free vs Premium)
- Email open rates (target: 40%+)
- Click-through rates (target: 15%+)
- Booking conversion rate (target: 3-5%)
- Revenue (MRR/ARR)

### Monitoring Services
- Vercel Analytics - Deployment & performance
- Beehiiv Dashboard - Email metrics
- Stripe Dashboard - Revenue & refunds
- Sentry (planned) - Error tracking

---

## 🧪 Testing

### Run Tests
```bash
npm test
```

### Test Coverage
We aim for 80%+ code coverage on:
- Deal detection algorithm
- Email API integration
- Subscription endpoints

### Manual Testing Checklist

Before each release:
- [ ] Email signup works
- [ ] Deal alert email sends
- [ ] Premium payment works (test mode)
- [ ] Unsubscribe link works
- [ ] Website is responsive (mobile/desktop)
- [ ] No console errors

---

## 📚 Documentation

- **[Beehiiv Setup](docs/BEEHIIV_SETUP.md)** - Email service configuration
- **[Implementation Guide](docs/IMPLEMENTATION.md)** - Architecture & technical decisions
- **[Content Strategy](docs/CONTENT_STRATEGY.md)** - Marketing & messaging
- **[API Reference](docs/API_REFERENCE.md)** - Endpoint documentation
- **[Brand Guidelines](docs/BRAND.md)** - Visual & tone guidelines

---

## 🚢 Deployment

### Development
```bash
npm run dev        # Local development server
```

### Staging (Preview Deployment via Vercel)
```bash
git push origin feature-branch   # Vercel auto-deploys
# View at: https://your-project-staging.vercel.app
```

### Production
```bash
git push origin main             # Auto-deploys to production
# View at: https://atlcheapflights.com
```

### Manual Deployment to Vercel
```bash
npm install -g vercel
vercel                           # Deploy current branch
vercel --prod                    # Deploy to production
```

---

## 🐛 Known Issues

- [ ] Websocket connection issues with Amadeus API (investigating)
- [ ] Email template rendering in Outlook (working on fix)

See [GitHub Issues](../../issues) for full list of blockers and bugs.

---

## 📞 Support & Questions

- **GitHub Issues**: Report bugs or request features
- **Discussions** (coming soon): Ask questions
- **Email**: support@atlcheapflights.com (when live)

---

## 📄 License

MIT License - See LICENSE file for details

---

## 🙏 Acknowledgments

Built with:
- Beehiiv for email infrastructure
- Amadeus for flight data
- Vercel for deployment
- The Atlanta travel community for inspiration

---

## 🗺️ Roadmap

### Q1 2025
- Complete Phase 2 development
- Beta test with 10 ATL travelers
- Launch public website

### Q2 2025
- Reach 500 free subscribers
- Launch referral program
- Expand to business class deals

### Q3 2025
- Reach 2,000 subscribers
- Premium subscriber milestone
- Launch mobile app (iOS/Android)

### Q4 2025
- Integrate MARTA/TSA real-time data
- Partner with ATL travel brands
- Establish ATL traveler community platform

---

## 💡 Contributing Ideas

Have ideas? We'd love to hear them!

**Planned Features:**
- [ ] SMS alerts for urgent deals
- [ ] Calendar integration (add to Google Calendar)
- [ ] Mobile app
- [ ] Social sharing
- [ ] Community deal verification

---

**Happy flying from ATL!** ✈️ 🍑

Last updated: October 2024  
Version: 0.1.0-alpha