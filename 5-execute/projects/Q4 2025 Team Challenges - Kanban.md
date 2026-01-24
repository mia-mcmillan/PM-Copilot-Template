---
kanban-plugin: board
project: Team Fitness Challenges MVP
jpd-id: OPP-101
owner: Product Team
status: in-progress
target-launch: 2025-12-15
tags:
  - kanban
  - execution
  - team-challenges
  - q4-2025
---

# Q4 2025: Team Challenges MVP - Kanban

**Project**: Team Fitness Challenges MVP (OPP-101)
**Target Launch**: December 15, 2025
**Status**: In Progress (Week 4 of 10)

---

## Backlog

- [ ] Rewards & prizes integration for challenge winners #feature @product due:2026-01-15 priority:low
- [ ] Custom challenge creation (admin-defined rules, metrics) #feature @product priority:medium
- [ ] Video workout library integration #content @product priority:low
- [ ] Garmin & Whoop wearable support #integration @engineering priority:medium
- [ ] Team formation algorithm optimization (balanced team assignments) #enhancement @engineering priority:low
- [ ] Push notification personalization (optimal send times) #enhancement @product priority:low

---

## To Do

- [ ] Design challenge completion celebration flow (confetti, badges, team victory screen) #design @alex due:2025-11-28 priority:high jira:TEMPO-156
- [ ] Spec admin dashboard export functionality (CSV, PDF for executive reports) #product @jordan due:2025-11-30 priority:high jira:TEMPO-189
- [ ] Write API documentation for HRIS integrations (Workday, BambooHR) #engineering @sam due:2025-12-02 priority:high jira:TEMPO-198
- [ ] Create onboarding tutorial flow (5-step guided tour for new users) #design @alex due:2025-12-03 priority:medium jira:TEMPO-167
- [ ] Set up Fitbit API credentials and test environment #engineering @maria due:2025-11-29 priority:high jira:TEMPO-203

---

## In Progress

- [ ] Mobile UI for team challenge leaderboard (real-time rankings, pull-to-refresh) #design @alex priority:critical jira:TEMPO-145 owner:Alex
- [ ] Backend API for team chat (WebSocket for real-time messaging, emoji reactions) #engineering @jordan priority:critical jira:TEMPO-178 owner:Jordan
- [ ] Apple HealthKit integration (step count, workout minutes, distance) #engineering @maria priority:critical jira:TEMPO-182 owner:Maria
- [ ] Admin dashboard MVP (participation metrics, engagement trends chart) #engineering @sam priority:high jira:TEMPO-191 owner:Sam

---

## Done

- [x] Customer validation interviews (5/5 HR Directors completed) #research @product owner:Product completed:2025-11-15
- [x] Competitive analysis (Wellable, Gympass, Peloton feature comparison) #research @product owner:Product completed:2025-11-10
- [x] JTBD analysis documented and reviewed #research @product owner:Product completed:2025-11-16
- [x] Pattern recognition analysis (Engagement Drop-off validated across 3 data sources) #research @product owner:Product completed:2025-11-20
- [x] Mobile app wireframes (15 core screens: onboarding, challenge dashboard, leaderboard, team chat, profile) #design @alex owner:Alex completed:2025-11-18
- [x] Technical architecture document (AWS infrastructure, API design, data models) #engineering @jordan owner:Jordan completed:2025-11-20
- [x] Database schema design (users, teams, challenges, activities, social_interactions tables) #engineering @maria owner:Maria completed:2025-11-21
- [x] iOS app skeleton (navigation, authentication, basic screens) #engineering @maria owner:Maria completed:2025-11-22
- [x] Android app skeleton (navigation, authentication, basic screens) #engineering @jordan owner:Jordan completed:2025-11-22
- [x] User authentication flow (email/password + SSO via Auth0) #engineering @sam owner:Sam completed:2025-11-23
- [x] Wearable integration research (Apple HealthKit vs. Fitbit API comparison, Terra API evaluation) #engineering @maria owner:Maria completed:2025-11-12
- [x] Challenge data model finalized (challenge types, scoring rules, team formation logic) #engineering @jordan owner:Jordan completed:2025-11-19
- [x] Design system components library (buttons, cards, typography, colors, icons) #design @alex owner:Alex completed:2025-11-25

---

## Notes & Decisions

**Week 4 Progress Update** (Nov 24-28):
- ✅ Authentication flow complete, both iOS and Android ready
- ✅ Design system finalized, engineering team unblocked
- 🚧 Apple HealthKit integration in progress, encountering permission edge cases
- 🚧 Leaderboard design nearly complete, awaiting feedback on ranking tie-breakers
- ⚠️ **Blocker**: Fitbit API access delayed (waiting on Fitbit developer approval, ETA Dec 2)
  - **Mitigation**: Prioritize manual entry fallback, launch with Apple Watch only if needed

**Key Decisions This Week**:
1. **Challenge Scoring**: Decided to use "points per capita" (total team points / team size) to prevent large teams from having unfair advantage [Decision Record: [[DR-001 - Team Scoring Normalization]]]
2. **Team Size Limits**: Set min team size = 5, max team size = 15 (optimal range based on usage data analysis) [Decision Record: [[DR-002 - Team Size Constraints]]]
3. **Manual Entry**: Allow manual workout entry for users without wearables (41% of beta users), with photo verification optional [Decision Record: [[DR-003 - Manual Entry Policy]]]

**Risks & Issues**:
- 🔴 **HIGH**: Fitbit API approval delayed (1 week behind schedule)
  - Impact: Launch with Apple Watch only initially
  - Action: Escalate with Fitbit dev relations, prepare manual entry as fallback
- 🟡 **MEDIUM**: Admin dashboard scope creep (stakeholders requesting 10+ new metrics)
  - Impact: Could delay MVP by 2 weeks
  - Action: Defer advanced metrics to V1.1 (post-launch), keep MVP scope tight
- 🟢 **LOW**: iOS App Store review concerns (may require privacy policy updates)
  - Impact: Minimal (privacy policy already drafted)
  - Action: Legal review scheduled for Dec 1

**Next Week Priorities** (Dec 1-5):
1. Complete leaderboard UI and backend integration
2. Ship team chat beta for internal testing
3. Finalize Apple HealthKit integration (handle all edge cases)
4. Begin QA testing on both iOS and Android
5. Prepare App Store submission materials (screenshots, descriptions, privacy policy)

---

## Team Members

**Product**: @product (Jordan - Product Lead)
**Design**: @alex (Alex - Product Designer, Contractor)
**Engineering**:
- @jordan (Jordan - Full-Stack Engineer, Backend + Android Lead)
- @maria (Maria - iOS Engineer + Wearable Integrations)
- @sam (Sam - Backend Engineer, API + Infrastructure)

**Stakeholders**: Sarah (VP Product), Michael (CTO), Emily (Head of Sales)

---

## Metrics Dashboard

**Velocity** (Week 4):
- Stories Completed: 3 (authentication, design system, data model)
- Stories In Progress: 4 (leaderboard, team chat, HealthKit, admin dashboard)
- Velocity Trend: On track (12 stories completed out of 40 total, 30% done in 40% of time)

**Timeline**:
- **Target Launch**: December 15, 2025 (3 weeks away)
- **Code Freeze**: December 10 (to allow 5 days for QA + app store approval)
- **Current Status**: On track (green)

**Scope Health**:
- **Original Scope**: 40 stories
- **Added**: 3 stories (challenge celebration, onboarding tutorial, manual entry)
- **Removed**: 2 stories (custom challenges, video library)
- **Net Change**: +1 story (manageable)

---

## Links

**Related Documents**:
- Opportunity: [[OPP-101 - Team Fitness Challenges]]
- Roadmap: [[2025-Q4 - Roadmap]]
- Technical Spec: [[Technical Architecture - Team Challenges MVP]]
- Design Files: [Figma - Team Challenges MVP](https://figma.com/file/example)

**External Links**:
- Jira Board: [TEMPO Project](https://tempo.atlassian.net)
- GitHub Repo: [tempo-mobile-app](https://github.com/tempo/mobile-app)
- Slack Channel: #team-challenges-mvp

---

**Tags**: #kanban #execution #team-challenges #mvp #in-progress #q4-2025