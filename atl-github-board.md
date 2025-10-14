# ATL Cheap Flights - GitHub Project Board Setup Guide

## 📋 Quick Start: Create Your GitHub Project Board

### Step 1: Create GitHub Repository
```bash
# If you haven't already
git init atl-cheap-flights
cd atl-cheap-flights
git remote add origin https://github.com/YOUR_USERNAME/atl-cheap-flights.git
git branch -M main
git push -u origin main
```

### Step 2: Set Up GitHub Project (Classic or New)

**Using GitHub Projects (Recommended - New Interface):**

1. Go to: `github.com/YOUR_USERNAME/atl-cheap-flights`
2. Click **"Projects"** tab → **"New project"**
3. Select **"Board"** template
4. Name it: `ATL Cheap Flights - Implementation`
5. Create 4 columns:
   - 📋 **Backlog**
   - 🔵 **In Progress**
   - 🟡 **Blocked**
   - ✅ **Done**

---

## 🎯 GitHub Issues Template for ATL Cheap Flights

### Issue Template 1: Features & Tasks

**File: `.github/ISSUE_TEMPLATE/feature.md`**

```markdown
---
name: Feature / Task
about: New feature, improvement, or task
title: "[FEATURE] "
labels: feature
assignees: ''
---

## Description
Brief description of what needs to be done.

## Phase
- [ ] Phase 1: Setup
- [ ] Phase 2: Development
- [ ] Phase 3: Testing
- [ ] Phase 4: Launch
- [ ] Phase 5: Growth

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Dependencies
- Depends on: #issue_number
- Blocks: #issue_number

## Resources / Links
- Documentation: [link]
- API Docs: [link]

## Notes
Any additional context or notes.
```

### Issue Template 2: Blockers

**File: `.github/ISSUE_TEMPLATE/blocker.md`**

```markdown
---
name: Blocker
about: Report a blocker preventing progress
title: "[BLOCKER] "
labels: blocker, urgent
assignees: ''
---

## What's Blocked?
Which issue or feature is blocked by this?

## The Problem
Describe the blocker in detail.

## Impact
How does this affect the timeline?

## Attempts Made
What have you tried so far?

## Needed to Unblock
What's required to resolve this?

## Current Status
- [ ] Waiting for: [person/thing]
- [ ] In investigation
- [ ] Needs decision
```

### Issue Template 3: Bugs

**File: `.github/ISSUE_TEMPLATE/bug.md`**

```markdown
---
name: Bug Report
about: Report a bug or issue
title: "[BUG] "
labels: bug
assignees: ''
---

## Description
What's the bug?

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Expected Behavior
What should happen?

## Actual Behavior
What actually happens?

## Environment
- OS: [e.g. macOS]
- Browser: [e.g. Chrome]
- Node version: [e.g. 18.0.0]

## Screenshots
If applicable, add screenshots.
```

---

## 📊 Initial Issues to Create (Copy/Paste)

### Phase 1: Setup & Infrastructure

**Issue 1: Beehiiv Publication Setup** 🟡 [IN PROGRESS - Your Current Task]
```
Title: [SETUP] Complete Beehiiv Publication Setup
Phase: Phase 1
Status: In Progress (you are here)
Labels: setup, beehiiv, in-progress

Tasks:
- [x] Create Beehiiv account
- [ ] Set up publication: "ATL Cheap Flights"
- [ ] Configure email templates (Free tier template, Premium tier template)
- [ ] Set up subscription tiers (Free & Premium)
- [ ] Generate API key
- [ ] Test API connection
- [ ] Set up webhook for subscriber events
- [ ] Configure Stripe integration
- [ ] Send test email
- [ ] Document credentials in .env template

Dependencies: None
Blocks: Issue #2 (Backend API Integration)
```

**Issue 2: Vercel & GitHub Setup**
```
Title: [SETUP] Deploy to Vercel & GitHub Integration
Phase: Phase 1
Labels: setup, vercel, deployment

Tasks:
- [ ] Create Vercel account
- [ ] Connect GitHub repo to Vercel
- [ ] Create environment variables in Vercel
- [ ] Configure auto-deployment on push
- [ ] Set up preview deployments
- [ ] Configure custom domain (atlcheapflights.com)
- [ ] Set up SSL certificate
- [ ] Test production deployment

Dependencies: GitHub repo created
Blocks: Phase 2 development
```

**Issue 3: Database Setup**
```
Title: [SETUP] Configure PostgreSQL Database
Phase: Phase 1
Labels: setup, database, postgres

Tasks:
- [ ] Create Vercel Postgres database (or Supabase)
- [ ] Generate connection credentials
- [ ] Create all tables (users, destinations, deals, email_campaigns, price_history)
- [ ] Set up database migrations
- [ ] Create seed data for testing
- [ ] Document connection string
- [ ] Test connection from local environment

Dependencies: Vercel setup
Blocks: Issue #4 (Backend API)
```

**Issue 4: Amadeus API Integration**
```
Title: [SETUP] Get Amadeus API Access & Test Flight Data
Phase: Phase 1
Labels: setup, amadeus, api

Tasks:
- [ ] Register for Amadeus Developer account
- [ ] Generate API keys (Client ID & Secret)
- [ ] Review API documentation
- [ ] Test Flight Offers Search endpoint
- [ ] Test with ATL → NYC route
- [ ] Document rate limits
- [ ] Set up API error handling
- [ ] Store credentials in .env

Dependencies: None
Blocks: Issue #5 (Deal Detection Algorithm)
```

### Phase 2: Development

**Issue 5: Deal Detection Algorithm**
```
Title: [FEATURE] Build Deal Detection Algorithm
Phase: Phase 2
Labels: feature, algorithm, backend

Tasks:
- [ ] Implement isDeal() function
- [ ] Create calculateDealScore() function
- [ ] Set 50% threshold rule
- [ ] Test with sample data
- [ ] Document algorithm logic
- [ ] Add unit tests
- [ ] Performance optimization

Dependencies: Issue #4 (Amadeus API)
Blocks: Issue #6 (Monitoring Service)
```

**Issue 6: Flight Monitoring Service**
```
Title: [FEATURE] Automated Flight Price Monitoring (Cron Job)
Phase: Phase 2
Labels: feature, backend, automation

Tasks:
- [ ] Set up node-cron or similar
- [ ] Create monitorFlights.js job
- [ ] Define 15-20 ATL routes to monitor
- [ ] Implement hourly price checks
- [ ] Store price history in database
- [ ] Integrate deal detection
- [ ] Test monitoring locally
- [ ] Deploy to Vercel (using serverless functions)

Dependencies: Issue #5 (Deal Detection)
Blocks: Issue #7 (Email Integration)
```

**Issue 7: Beehiiv Backend Integration**
```
Title: [FEATURE] Integrate Beehiiv API for Email Sending
Phase: Phase 2
Labels: feature, beehiiv, api

Tasks:
- [ ] Create beehiiv.js service file
- [ ] Build addSubscriber() function
- [ ] Build sendDealAlert() function
- [ ] Create email HTML template
- [ ] Test adding subscriber
- [ ] Test sending sample deal alert
- [ ] Implement error handling
- [ ] Add rate limiting

Dependencies: Issue #1 (Beehiiv Setup), Issue #6 (Monitoring Service)
Blocks: Issue #8 (Website Integration)
```

**Issue 8: Website Frontend - Deal Display & Signup**
```
Title: [FEATURE] Build Frontend: Deal Cards & Email Signup
Phase: Phase 2
Labels: feature, frontend, react

Tasks:
- [ ] Create Next.js pages structure
- [ ] Build deal card components
- [ ] Build signup form component
- [ ] Implement destination selector (Domestic/International tabs)
- [ ] Create pricing modal component
- [ ] Integrate with /api/subscribe endpoint
- [ ] Add form validation
- [ ] Test with real data

Dependencies: Issue #7 (Beehiiv Integration)
Blocks: Phase 3 testing
```

**Issue 9: Website Styling & Brand Integration**
```
Title: [FEATURE] Apply ATL Cheap Flights Brand Design
Phase: Phase 2
Labels: feature, design, frontend

Tasks:
- [ ] Apply custom color palette (#042576, #78ADD1, #B01534)
- [ ] Implement Lobster Two header font
- [ ] Implement Noto Sans body font
- [ ] Implement Futura Bold for CTAs
- [ ] Create consistent spacing & layout
- [ ] Mobile responsiveness testing
- [ ] Color contrast accessibility check
- [ ] Brand consistency across all pages

Dependencies: Issue #8 (Frontend Build)
Blocks: Phase 3 testing
```

### Phase 3: Testing & Refinement

**Issue 10: Email Testing & Optimization**
```
Title: [TEST] Test Email Campaigns & Optimize Delivery
Phase: Phase 3
Labels: testing, email, beehiiv

Tasks:
- [ ] Send test deal alert to yourself
- [ ] Verify email formatting
- [ ] Test unsubscribe link
- [ ] Test all CTAs
- [ ] Verify branding in email
- [ ] Test on mobile email client
- [ ] Check spam score
- [ ] Set up email analytics tracking

Dependencies: Issue #7 (Beehiiv Integration)
Blocks: Beta launch
```

**Issue 11: Beta Testing with 10 Users**
```
Title: [TEST] Beta Testing Round 1 (10 Users)
Phase: Phase 3
Labels: testing, qa, beta

Tasks:
- [ ] Recruit 10 beta testers from Atlanta
- [ ] Send signup link
- [ ] Monitor for 2 weeks
- [ ] Send first 3 real deal alerts
- [ ] Collect feedback via survey
- [ ] Track signup/engagement metrics
- [ ] Document bugs found
- [ ] Iterate on feedback

Dependencies: All Phase 2 tasks
Blocks: Public launch
```

**Issue 12: Website Performance Optimization**
```
Title: [TEST] Performance Testing & Optimization
Phase: Phase 3
Labels: testing, performance, frontend

Tasks:
- [ ] Test Lighthouse scores
- [ ] Optimize bundle size
- [ ] Test page load times
- [ ] Test on slow networks
- [ ] Implement lazy loading
- [ ] Optimize images
- [ ] Database query optimization
- [ ] API response time optimization

Dependencies: Issue #8 (Frontend)
Blocks: Public launch
```

### Phase 4: Launch

**Issue 13: Public Website Launch**
```
Title: [LAUNCH] Deploy Public Website
Phase: Phase 4
Labels: launch, deployment

Tasks:
- [ ] Final QA check
- [ ] Deploy to production
- [ ] Verify all systems operational
- [ ] Check SSL certificate
- [ ] Test from different geographic locations
- [ ] Monitor error logs
- [ ] Set up uptime monitoring
- [ ] Send launch announcement email

Dependencies: Issues #10, #11, #12 (All Phase 3 complete)
Blocks: Marketing phase
```

**Issue 14: SEO & Analytics Setup**
```
Title: [LAUNCH] Configure SEO & Analytics
Phase: Phase 4
Labels: launch, seo, analytics

Tasks:
- [ ] Install Google Analytics
- [ ] Set up conversion tracking
- [ ] Create sitemap.xml
- [ ] Create robots.txt
- [ ] Set up Google Search Console
- [ ] Optimize meta descriptions
- [ ] Configure Vercel Analytics
- [ ] Set up error tracking (Sentry)

Dependencies: Issue #13 (Website Launch)
Blocks: Growth phase
```

### Phase 5: Growth & Marketing

**Issue 15: Marketing Campaign Execution**
```
Title: [GROWTH] Execute Initial Marketing Campaigns
Phase: Phase 5
Labels: growth, marketing

Tasks:
- [ ] Create Reddit posts in r/Atlanta
- [ ] Post in r/TravelDeals
- [ ] Create Instagram content (10 reels)
- [ ] Create TikTok content (10 videos)
- [ ] Reach out to ATL travel bloggers
- [ ] Join Facebook ATL travel groups
- [ ] Send launch email to personal network
- [ ] Track results & metrics

Dependencies: Issue #13 (Public Launch)
Related: Issue #15 (Content & Campaign Planning)
```

**Issue 16: Referral Program Setup**
```
Title: [FEATURE] Build Referral Program
Phase: Phase 5
Labels: feature, growth, monetization

Tasks:
- [ ] Design referral mechanics
- [ ] Create referral landing page
- [ ] Build referral tracking in database
- [ ] Set up reward system
- [ ] Create referral share links
- [ ] Test end-to-end
- [ ] Create marketing materials

Dependencies: Issue #15 (Marketing)
Blocks: None (ongoing)
```

---

## 🔄 GitHub Project Board Workflow

### How to Use the Board:

1. **Create Issues** from the templates above
2. **Add to Project** → drag to appropriate column
3. **Assign Issues** to yourself or team members
4. **Link Issues** with dependencies (use "relates to", "blocks", "depends on")
5. **Update Status** as you progress

### Daily Workflow:
- Start of day: Check "🔵 In Progress" column
- Throughout day: Move issues to "✅ Done" as completed
- End of day: Move next priority to "🔵 In Progress"
- When stuck: Create "🟡 Blocked" issue and comment with what's needed

### Weekly Review:
- Check "🟡 Blocked" column for unresolved blockers
- Update timeline estimates
- Plan next week's priorities

---

## 📝 Beehiiv Setup Checklist (Your Current Task)

### What You Need to Complete:

```markdown
## Beehiiv Setup Progress

### Account & Publication
- [ ] Create Beehiiv account (if not done)
- [ ] Create publication: "ATL Cheap Flights"
- [ ] Configure basic publication settings

### Email Templates
- [ ] Design "Free Tier" welcome email
- [ ] Design "Premium Tier" welcome email
- [ ] Create deal alert email template
  - Subject: "🔥 ATL Deal Alert: [Destination] for $[Price]"
  - Brand with #042576 (Chiefs Blue) header
  - Include pricing, dates, booking link
  - Footer with unsubscribe & manage preferences
- [ ] Test email rendering

### Subscription Tiers
- [ ] Create "ATL Free" tier ($0)
- [ ] Create "ATL Premium" tier ($49/year or $4.99/month)
- [ ] Configure tier features & benefits

### API Setup
- [ ] Generate API key
- [ ] Document API key (add to .env.local)
- [ ] Test API authentication
- [ ] Set up webhook URL (when backend ready)

### Stripe Integration
- [ ] Connect Stripe account to Beehiiv
- [ ] Configure payment processor
- [ ] Set up billing preferences
- [ ] Test payment flow with test card

### Documentation
- [ ] Create BEEHIIV_SETUP.md with instructions
- [ ] Document API endpoints used
- [ ] List custom fields set up
- [ ] Create troubleshooting guide
```

---

## 🎯 Next Steps (In Order)

1. **Finish Beehiiv Setup** (YOU ARE HERE)
   - Tell me which step you're stuck on
   - I'll walk you through it

2. **Create GitHub Repo** with this structure:
   ```
   atl-cheap-flights/
   ├── .github/
   │   ├── ISSUE_TEMPLATE/
   │   │   ├── feature.md
   │   │   ├── blocker.md
   │   │   └── bug.md
   │   └── workflows/
   ├── README.md
   ├── BEEHIIV_SETUP.md
   ├── IMPLEMENTATION.md
   ├── .env.example
   └── docs/
   ```

3. **Create GitHub Project Board**
   - Use the issues listed above
   - Set up the 4-column board
   - Move current issues to "In Progress"

4. **Start Phase 2 Development**
   - Begin with Issue #5 (Deal Detection)
   - Then Issue #6 (Monitoring Service)

---

## 💡 Tips for Success

- **Use milestones**: Group issues by phase for better tracking
- **Link issues**: Use "Depends on" and "Blocks" to show relationships
- **Add labels**: Use phase labels + type labels (feature, bug, setup)
- **Use assignees**: Assign issues to yourself or team members
- **Weekly reviews**: Check progress on Friday
- **Update descriptions**: Keep details current as you learn

