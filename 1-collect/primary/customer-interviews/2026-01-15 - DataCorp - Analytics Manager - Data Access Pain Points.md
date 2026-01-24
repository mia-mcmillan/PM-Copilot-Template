---
author: Mia McMillan
created: 2026-01-15
interview-date: 2026-01-15
interviewee: Sarah Chen
interviewee-role: Analytics Manager
interviewee-company: DataCorp
interview-type: Discovery Interview
status: transcribed
tags: [data-access, self-service, governance, customer-interview]
---

# Customer Interview: DataCorp - Analytics Manager

**Date:** January 15, 2026
**Interviewee:** Sarah Chen, Analytics Manager
**Company:** DataCorp (500 employees, B2B SaaS)
**Duration:** 45 minutes
**Interviewer:** Mia McMillan
**Interview Type:** Discovery - Data Access Pain Points

## Company Context

DataCorp is a B2B SaaS company providing supply chain analytics. Sarah's team of 8 analysts supports 200+ internal business users across sales, operations, and finance departments. They use our data platform for business intelligence and reporting.

## Interview Transcript

### Opening - Current Role and Responsibilities

**Mia:** Thanks for taking the time today, Sarah. Can you start by telling me about your role and what your typical day looks like?

**Sarah:** Sure! I manage a team of 8 analysts, and we're basically the bridge between our business teams and the data. We spend most of our time fielding requests - someone in sales wants a customer report, operations needs shipment metrics, finance wants revenue breakdowns. It's constant.

**Mia:** How many requests would you say you get in a typical week?

**Sarah:** Oh God, probably 30-40 requests. Some are quick - "can you pull last month's numbers?" - but others are complex analyses that take days. The problem is, we're spending so much time on the simple stuff that we barely have time for the strategic work.

### Current Process and Workflow

**Mia:** Walk me through what happens when someone needs data. What's the process?

**Sarah:** It's painful, honestly. They'll send an email or Slack message - sometimes both - saying "I need data on X." Then I have to figure out what they actually need because their request is usually too vague. Like, someone will say "I need customer data" and I'm thinking... which customers? What metrics? What time period? What are you trying to decide?

So first, I spend 20 minutes going back and forth clarifying. Then I queue it up for one of my analysts. They write a SQL query, run it, export to CSV, email it back. The whole thing takes anywhere from 2 hours to 2 days depending on complexity and our backlog.

**Mia:** What happens if they need changes or have follow-up questions?

**Sarah:** *laughs* Then we start all over again! That's the most frustrating part. They'll come back and say "actually, can you add this column?" or "can you filter it differently?" and we're back in the queue. I swear, 60% of our requests are just iterations on previous requests.

### Pain Points and Frustrations

**Mia:** What's the most frustrating part of this process for you?

**Sarah:** The bottleneck. We're the bottleneck for the entire company. Every decision that needs data has to wait for my team. And I know the business users are frustrated too - they'll Slack me asking "when will this be ready?" and I'm like, "you're number 12 in the queue."

But here's the thing - half of these requests are things they could do themselves if they had access to the data. Like, pulling last month's sales by region? That's a simple query. But we can't just give them database access because... well, security. They don't understand SQL. They might break something. And honestly, they'd probably make mistakes and trust bad data.

**Mia:** Tell me more about the security concern.

**Sarah:** Our data warehouse has everything - customer PII, financials, internal metrics. We can't just open that up to everyone. But at the same time, most people only need a small slice of the data. Sales needs sales data. Finance needs financial data. But right now, it's all or nothing - either you have no access and wait for my team, or you're a data analyst with full access.

### Workarounds and Current Solutions

**Mia:** Have you tried any workarounds or solutions to address this?

**Sarah:** Oh yeah, we've tried a bunch of things. We built some Tableau dashboards for common questions - like weekly sales metrics, top customers, stuff like that. That helped reduce maybe 20% of requests.

We also created a bunch of scheduled reports that email out automatically. But the problem is, those are static. The moment someone wants to filter differently or add a dimension, they're back to requesting custom pulls from us.

Some of the more technical business users have learned to use our BI tool, but that's only 5-10 people out of 200. Most people don't want to learn a new tool - they just want their data in Excel where they already work.

**Mia:** What about the more technical users - what's their experience like?

**Sarah:** They're actually more frustrated in some ways because they know enough to be dangerous. They'll try to build their own queries in Tableau and end up with wrong results because they don't understand how the data model works. Then decisions get made on bad data, and I find out about it weeks later when something doesn't add up.

I've had to become the data police, which I hate. I'm constantly saying "where did you get those numbers?" and correcting analyses. It's not sustainable.

### Emotional Impact

**Mia:** How does this situation make you feel as a manager?

**Sarah:** Honestly? Burned out. My team is burned out. We got into analytics because we wanted to find insights and drive strategy. Instead, we're data janitors. We're copy-pasting data all day.

And I feel guilty because I know I'm blocking people. Like, the VP of Sales needed data for a board presentation last week, and I had to tell him it would take 2 days because we were slammed. He was clearly annoyed, and I don't blame him. He's trying to run his business.

**Mia:** What about your team members?

**Sarah:** Two of my best analysts quit last quarter. When I asked why, they said they felt like glorified report writers, not analysts. One of them literally said "I'm just a middleman - I take a request, write SQL, send results. A trained monkey could do this."

That hurt because he's right. They're capable of so much more - predictive modeling, churn analysis, market segmentation. But we spend 80% of our time on basic data pulls.

### Ideal State / Desired Outcome

**Mia:** If you could wave a magic wand, what would the ideal state look like?

**Sarah:** People could get their own data for simple questions. Like, if you need last month's sales, you should be able to pull that yourself in 30 seconds without waiting for my team. Self-service, but safe.

And by safe, I mean they can only see data they're allowed to see. Sales sees sales data. Finance sees financial data. And the data is governed - they're getting it from the right source, it's clean, it's trusted.

**Mia:** What would that free up your team to do?

**Sarah:** The actual analytical work! We could focus on "why are sales declining in this region?" instead of "what were sales in this region?" We could build predictive models, identify opportunities, actually move the needle on the business.

I want my team to be strategic partners, not a service desk.

### Technical Requirements and Constraints

**Mia:** What would need to be true for you to feel comfortable with people self-serving data?

**Sarah:** Three things: access controls, ease of use, and governance.

**Access controls** - I need to know that Sarah in Sales can only see sales data, not HR data or financial forecasts. Row-level security, column-level security, the works.

**Ease of use** - it can't require learning SQL or understanding our data model. If people need training, they won't use it. It needs to be as easy as searching Google - "show me sales last month" and boom, there it is.

**Governance** - I need to trust the data they're getting is correct. If someone pulls a "customer count" metric, I need to know they're using the same definition we use. Otherwise, we're back to people making decisions on bad data.

**Mia:** What about your team's workflow - how would that need to change?

**Sarah:** We'd become more like consultants or data stewards. Instead of "pull this data for me," requests would be "help me understand why sales are declining" or "can you validate my analysis?" Much more strategic conversations.

We'd also curate and maintain the data catalog - make sure data is properly documented, definitions are clear, quality is high. Set people up for success with self-service.

### Success Criteria

**Mia:** How would you know if this was working? What metrics would tell you it's successful?

**Sarah:** Easy - request volume. If we're getting 30-40 requests per week now, I'd want to cut that in half in the first quarter. Maybe down to 10-15 requests per week, and those would be the complex, strategic asks.

I'd also look at time-to-data. Right now, average turnaround is 1-2 days for simple requests. If people can self-serve, time-to-data should be minutes, not days.

And honestly, I'd measure my team's happiness. If they're doing more strategic work and less grunt work, I'd see that in retention and engagement.

**Mia:** What about business impact?

**Sarah:** Faster decisions. Right now, decisions wait for data. If the VP of Sales can pull data in real-time during a meeting, decisions happen faster. That's huge.

I'd also expect to see better data literacy across the company. When people can explore data themselves, they start asking better questions. They become more data-driven naturally.

### Fears and Concerns

**Mia:** What worries you about giving people more direct access to data?

**Sarah:** *pauses* My biggest fear is that people will make decisions on wrong data and I won't know about it. Like, someone builds a "customer lifetime value" analysis but uses the wrong formula, and we change our entire pricing strategy based on bad math.

I also worry about people misinterpreting data. Data without context is dangerous. If sales dropped 20% in December, is that bad? Well, it depends - December is usually slow, so 20% down might actually be good compared to last December. But someone might see that and panic.

**Mia:** How would you want to mitigate those concerns?

**Sarah:** I'd need visibility into what people are doing. Like, if someone runs a query or builds an analysis, I should be able to see it and validate it if needed. Not to police them, but to help them.

And there'd need to be some kind of certification or approval process for certain types of analyses. If you're building a report that goes to executives, maybe that needs to be reviewed by my team first.

### Competitive Context

**Mia:** Have you looked at other tools or solutions?

**Sarah:** Oh yeah, we've tried a few things. We looked at Looker, but it's too complex for our business users. We tried Power BI, but the governance model didn't work for us - it's too easy to create shadow reports with bad data.

We also looked at some of the AI-powered analytics tools that let you ask questions in natural language. Those are cool in demos, but when we tested them, the accuracy was like 60%. Can't trust that for business decisions.

**Mia:** What made those solutions not work for you?

**Sarah:** They all optimize for one thing - either ease of use, or governance, or power. But we need all three. Easy enough for non-technical users, governed enough for me to trust it, powerful enough for my analysts.

Most tools feel like they're built for data analysts, not business users. Or they're built for business users but treat my team like we don't exist.

### Willingness to Pay / Budget

**Mia:** If a solution solved these problems, what would that be worth to your organization?

**Sarah:** *thinks* Well, my team costs about $800K per year in salaries. If we could free up 50% of their time for strategic work, that's $400K in value right there. Plus the opportunity cost of faster decisions - probably another $200K-$500K in revenue impact.

So if a solution cost, I don't know, $50K-$100K per year and actually solved this? That's a no-brainer ROI. I'd pay for it out of my budget today.

**Mia:** What would need to be true for you to advocate for this purchase?

**Sarah:** I'd need proof that it works - like, a pilot with my sales team for 30 days. Show me that request volume goes down, time-to-data goes down, and data quality stays high or improves. If I can see that in real numbers, I'll take it to my VP and get budget.

### Closing - Priority and Timeline

**Mia:** On a scale of 1-10, how urgent is solving this problem?

**Sarah:** 9. Maybe even 10. We're losing good people, we're blocking the business, and I'm drowning. I can't keep doing this for another year.

**Mia:** If you could have this solved, when would you want it?

**Sarah:** Yesterday. *laughs* But realistically, if we could pilot something in Q1 and roll it out in Q2, that would be huge. We're planning our budget for next fiscal year right now, so timing is actually perfect.

**Mia:** Last question - if I could only solve one pain point for you, what would it be?

**Sarah:** Get simple data requests off my team's plate. Let people self-serve the basics - sales numbers, customer counts, whatever. That alone would free up probably 40% of our time. Everything else we can figure out after that.

---

## Key Insights

### Jobs-to-be-Done

**Functional Jobs:**
- Enable business users to access data quickly without analyst intervention
- Reduce bottleneck on analytics team for simple data requests
- Ensure data accuracy and consistency across self-service access
- Maintain security and governance while expanding access
- Free up analysts for strategic work vs. data pulls

**Emotional Jobs:**
- Feel empowered rather than blocked when needing data
- Trust that data is correct and governed
- Feel valued as an analytics professional (not just a data janitor)
- Reduce burnout and improve team morale
- Feel confident decisions are based on accurate data

**Social Jobs:**
- Be seen as enabling the business rather than blocking it
- Position analytics team as strategic partners, not a service desk
- Demonstrate value as a manager by improving team output
- Earn trust from business stakeholders

### Pain Points

1. **Bottleneck:** Analytics team is a bottleneck for all data access (30-40 requests/week)
2. **Simple vs. Complex:** 60% of requests are basic data pulls that could be self-service
3. **Iteration Cycles:** Constant back-and-forth for clarifications and changes
4. **Security vs. Access:** Can't give database access due to security, but that blocks productivity
5. **Data Quality:** Business users creating incorrect analyses when they try to self-serve
6. **Burnout:** Team feels like "data janitors" rather than analysts
7. **Retention:** Lost 2 best analysts who felt underutilized
8. **Slow Decisions:** Business decisions delayed 1-2 days waiting for data

### Current Workarounds

- Tableau dashboards for common questions (reduces ~20% of requests)
- Scheduled email reports (static, limited flexibility)
- 5-10 technical users use BI tool (often create incorrect analyses)
- Manual email/Slack request queue

### Success Criteria

- Cut request volume from 30-40/week to 10-15/week (50% reduction)
- Reduce time-to-data from 1-2 days to minutes for simple requests
- Improve team retention and engagement
- Enable faster business decisions
- Increase data literacy across organization

### Buying Triggers

- Budget planning happening now for next fiscal year
- Recent loss of 2 key analysts
- VP-level frustration with data access delays
- Team burnout at critical level

### Willingness to Pay

- $50K-$100K annual budget available
- ROI case: $400K+ in team time value + $200K-$500K in faster decisions
- Would approve from existing budget with proof of concept

### Requirements

**Must-Have:**
1. Row-level and column-level security (role-based access)
2. Easy to use without SQL knowledge (Google-search simple)
3. Governed data with trusted definitions
4. Visibility into usage for analytics team
5. Validation/approval workflow for executive reports

**Nice-to-Have:**
- Natural language queries (if accuracy >95%)
- Integration with existing tools (Tableau, Excel)
- Data catalog and documentation
- Usage analytics for analytics team

### Decision Process

- 30-day pilot with sales team
- Proof points: reduced request volume, maintained data quality, faster time-to-data
- Needs VP approval for budget (but would advocate with strong pilot results)
- Timeline: Pilot in Q1, rollout in Q2

### Competitive Intelligence

- Tried Looker (too complex for business users)
- Tried Power BI (governance concerns, shadow reports)
- Tried AI analytics tools (60% accuracy, not trustworthy)
- Gap: No tool balances ease of use + governance + power

---

## Follow-Up Actions

- [ ] Share prototype of self-service access with row-level security
- [ ] Propose 30-day pilot with DataCorp sales team (5-10 users)
- [ ] Prepare metrics dashboard to track: request volume, time-to-data, data quality
- [ ] Schedule follow-up with Sarah in 2 weeks to discuss pilot structure