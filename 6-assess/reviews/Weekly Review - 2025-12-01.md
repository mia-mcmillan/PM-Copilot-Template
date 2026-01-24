---
date: 2025-12-01
week: Week of November 24-30, 2025
reviewer: Product Team
status: published
tags:
  - weekly-review
  - q4-2025
  - team-challenges
---

# Weekly Review: November 24-30, 2025

**Week of**: November 24-30, 2025
**Reviewer**: Product Team
**Status**: Published

---

## TL;DR (Executive Summary)

**🟢 Overall Status**: On track for December 15 MVP launch

**Key Wins**:
- Authentication flow shipped for iOS + Android
- Design system finalized, eng team unblocked
- 3/5 core features complete (auth, data models, design system)

**Key Challenges**:
- Fitbit API approval delayed 1 week (low risk - have mitigation)
- Admin dashboard scope creep concerns (contained)

**Next Week Focus**:
- Ship leaderboard UI + backend integration
- Complete Apple HealthKit integration
- Begin QA testing (both iOS + Android)

---

## Progress This Week

### Shipped ✅

**Engineering**:
1. **User Authentication Flow** (Sam, completed Nov 23)
   - Email/password + SSO via Auth0
   - Works on both iOS and Android
   - Security review passed

2. **Design System Components** (Alex, completed Nov 25)
   - Button, card, typography, color, icon libraries
   - Documented in Figma + Storybook
   - Engineering team now unblocked for all UI work

3. **Challenge Data Model** (Jordan, completed Nov 19)
   - Database schema finalized
   - Challenge types, scoring rules, team formation logic
   - Reviewed and approved by tech lead

### In Progress 🚧

**Engineering**:
1. **Team Challenge Leaderboard** (Alex + Jordan, ~80% complete)
   - UI design nearly done (awaiting feedback on tie-breaker ranking)
   - Backend API in progress (WebSocket for real-time updates)
   - ETA: Dec 3

2. **Apple HealthKit Integration** (Maria, ~60% complete)
   - Core integration working (step count, workout minutes, distance)
   - Encountering permission edge cases (handling user denials gracefully)
   - ETA: Dec 4

3. **Team Chat Feature** (Jordan, ~50% complete)
   - WebSocket infrastructure set up
   - Working on emoji reactions and real-time message delivery
   - ETA: Dec 5

4. **Admin Dashboard MVP** (Sam, ~40% complete)
   - Participation metrics chart working
   - Engagement trends visualization in progress
   - ETA: Dec 8

---

## Blockers & Risks

### 🔴 HIGH Priority

**Fitbit API Approval Delayed**
- **Issue**: Waiting on Fitbit developer portal approval (expected Nov 27, now Dec 2)
- **Impact**: 1 week delay on Fitbit integration
- **Mitigation**:
  - Launch with Apple Watch only initially (80% market coverage)
  - Prioritize manual entry fallback (works for 41% of users without wearables)
  - Escalated with Fitbit dev relations team
- **Status**: Being monitored, low risk to launch date

### 🟡 MEDIUM Priority

**Admin Dashboard Scope Creep**
- **Issue**: Stakeholders requesting 10+ additional metrics beyond MVP scope
- **Impact**: Could delay MVP by 2 weeks if not contained
- **Mitigation**:
  - Met with stakeholders, agreed to defer advanced metrics to V1.1 (post-launch)
  - Documented "MVP vs. V1.1" feature list for transparency
  - Committed to shipping V1.1 within 4 weeks of MVP launch
- **Status**: Resolved, scope locked for MVP

### 🟢 LOW Priority

**iOS App Store Review Concerns**
- **Issue**: May require privacy policy updates before approval
- **Impact**: Minimal (1-2 day delay at most)
- **Mitigation**: Privacy policy already drafted, legal review scheduled Dec 1
- **Status**: Proactive, no immediate concern

---

## Key Decisions Made

**Decision 1: Team Scoring Normalization** [[DR-001]]
- **Context**: Large teams (15 people) had unfair advantage over small teams (5 people) in raw point totals
- **Decision**: Use "points per capita" (total team points / team size) for leaderboard ranking
- **Rationale**: Ensures fair competition regardless of team size
- **Impact**: Requires backend scoring logic update (2-day effort, already in progress)

**Decision 2: Team Size Constraints** [[DR-002]]
- **Context**: Usage data shows optimal team size for engagement is 5-8 members
- **Decision**: Set min team size = 5, max team size = 15
- **Rationale**:
  - Too small (2-3): Not enough social pressure
  - Too large (20+): Diffusion of responsibility ("someone else will do it")
  - 5-15 is sweet spot for accountability + connection
- **Impact**: Product spec updated, team formation algorithm adjusted

**Decision 3: Manual Entry Policy** [[DR-003]]
- **Context**: 41% of beta users don't have wearables, but still want to participate
- **Decision**: Allow manual workout entry with optional photo verification
- **Rationale**: Inclusive design (democratize wellness), trust-based approach
- **Impact**: Design + backend work (3-day effort, added to sprint)

---

## Metrics & Progress Tracking

### Sprint Progress (Week 4 of 10)

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Stories Completed | 3 | 3 | 🟢 On track |
| Stories In Progress | 4 | 4 | 🟢 On track |
| Velocity (% done) | 30% | 30% (12/40 stories) | 🟢 On track |
| Timeline | Dec 15 launch | Dec 15 (3 weeks away) | 🟢 On track |
| Scope Change | 0 net stories | +1 net story | 🟡 Acceptable |

**Interpretation**: On track for December 15 launch. Velocity is healthy (30% done in 40% of time = ahead of pace). Scope change (+1 story) is manageable.

### Customer Validation Progress

| Activity | Target | Actual | Status |
|----------|--------|--------|--------|
| Customer Interviews | 5 | 5 | ✅ Complete |
| Usage Data Analysis | 450+ users | 450 users | ✅ Complete |
| Pattern Validation | 3 data sources | 3 sources | ✅ Complete |
| Pilot Prospects | 20 | 23 | 🟢 Ahead |

**Interpretation**: Customer validation complete. Pilot pipeline is healthy (23 prospects for 20 pilot slots).

---

## Next Week Priorities (Dec 1-7)

### Must Ship (Critical Path)

1. **Complete Leaderboard** (Alex + Jordan)
   - Finalize UI design (resolve tie-breaker ranking)
   - Ship backend API integration
   - Internal testing with real data

2. **Ship Apple HealthKit Integration** (Maria)
   - Handle all permission edge cases
   - Test with 10+ device configurations
   - Document known limitations

3. **Begin QA Testing** (All Engineering)
   - iOS: Test on 5+ device types (iPhone 12, 13, 14, 15, SE)
   - Android: Test on 3+ device types (Pixel, Samsung, OnePlus)
   - Smoke test all critical flows (signup, join challenge, log workout, view leaderboard)

### Should Complete (High Priority)

4. **Team Chat Beta** (Jordan)
   - Ship internal beta for team testing
   - Gather feedback on UX, performance, reliability
   - Iterate based on feedback

5. **Admin Dashboard MVP** (Sam)
   - Complete participation metrics view
   - Add engagement trends chart
   - Prepare demo for stakeholder review (Dec 6)

### Nice to Have (Medium Priority)

6. **Prepare App Store Submission** (Maria + Sam)
   - Screenshots (iOS + Android)
   - App descriptions
   - Privacy policy final review
   - Submit for review by Dec 10 (5-day buffer for approval)

---

## Learning & Insights

### What Went Well This Week 🎉

1. **Design System Delivered Early**: Alex shipped design system 2 days ahead of schedule, unblocking eng team
2. **Cross-Functional Collaboration**: Daily standups improved communication (eng + design sync'd well on leaderboard)
3. **Proactive Risk Management**: Identified Fitbit API delay early, had mitigation plan ready

### What Could Be Better 🤔

1. **Stakeholder Alignment**: Admin dashboard scope creep happened because we didn't align on MVP definition upfront
   - **Action**: Create "MVP Definition" doc at start of every project (what's in, what's out, why)

2. **Edge Case Discovery**: Apple HealthKit permission edge cases discovered late (week 4 vs. week 2)
   - **Action**: Allocate more time for integration testing upfront (don't assume APIs "just work")

3. **Dependency Tracking**: Fitbit API approval was external dependency we didn't track proactively
   - **Action**: Create "External Dependencies" tracker at project kickoff (APIs, legal, partnerships)

### Key Insights from Customer Conversations

**Insight 1**: HR leaders care MORE about "time to value" than "feature completeness"
- **Evidence**: Sarah (Acme Corp) said "I don't have bandwidth for month-long implementations"
- **Implication**: Prioritize onboarding speed and "5-minute setup" experience in MVP
- **Action**: Added "onboarding tutorial" task to backlog (5-step guided tour)

**Insight 2**: "Team chat" is surprisingly high-value (not just nice-to-have)
- **Evidence**: Beta users say "The trash talk in our team chat is the best part"
- **Implication**: Team chat drives engagement (not just leaderboard competition)
- **Action**: Elevated team chat to "critical path" (was originally "nice to have")

**Insight 3**: Manual entry is not a compromise, it's a feature
- **Evidence**: 41% of beta users prefer manual entry (more flexibility, no wearable required)
- **Implication**: Position as "works with or without wearables" (not "wearable-first, manual fallback")
- **Action**: Design manual entry UX as first-class experience (not afterthought)

---

## Shoutouts & Wins 🙌

- **Alex (Design)**: Shipped design system early, unblocking eng team for all UI work
- **Sam (Engineering)**: Auth flow shipped with zero bugs, passed security review on first try
- **Jordan (Engineering)**: Great technical leadership on data model design (clean, scalable, well-documented)
- **Maria (Engineering)**: Proactive communication on HealthKit integration challenges (no surprises)

---

## Looking Ahead: Next 2 Weeks

**Week of Dec 1-7**: **Build**
- Complete all core features (leaderboard, HealthKit, team chat, admin dashboard)
- Begin QA testing (iOS + Android)
- Prepare App Store submission materials

**Week of Dec 8-14**: **Polish & Ship**
- Code freeze Dec 10
- Final QA testing (Dec 10-12)
- App Store submission (Dec 10)
- Launch prep: customer emails, demo videos, support docs
- **Launch: December 15, 2025**

---

## Action Items

**Product Team**:
- [ ] Schedule stakeholder demo for admin dashboard (Dec 6) @product
- [ ] Create "MVP Definition" doc template for future projects @product
- [ ] Draft customer onboarding emails for Dec 15 launch @product

**Engineering**:
- [ ] Resolve leaderboard tie-breaker ranking logic @jordan due:2025-12-02
- [ ] Complete Apple HealthKit edge case handling @maria due:2025-12-04
- [ ] Set up QA test devices (iOS + Android) @sam due:2025-12-01
- [ ] Create "External Dependencies" tracker for future projects @jordan

**Design**:
- [ ] Finalize leaderboard UI based on eng feedback @alex due:2025-12-02
- [ ] Create App Store screenshots (iOS + Android) @alex due:2025-12-08

---

## Related Documents

- **Project Kanban**: [[Q4 2025 Team Challenges - Kanban]]
- **Opportunity**: [[OPP-101 - Team Fitness Challenges]]
- **Roadmap**: [[2025-Q4 - Roadmap]]
- **Decision Records**: [[DR-001 - Team Scoring]] | [[DR-002 - Team Size Constraints]] | [[DR-003 - Manual Entry]]
- **Previous Review**: [[Weekly Review - 2025-11-24]]
- **Next Review**: [[Weekly Review - 2025-12-08]]

---

**Tags**: #weekly-review #q4-2025 #team-challenges #mvp #on-track