# HotWax Commerce — Instance Types: 

> **Who is this for?** Anyone working with HotWax Commerce — whether you're in operations, QA, business, or tech. No technical background required.

---

## What Is It? (The Simple Explanation)

Think of HotWax Commerce like a **retail store with three versions of its own floor plan**:

| Version | Real-World Analogy |
|---|---|
|  **Development** | The back room where staff try new shelf arrangements — nothing is open to the public yet |
|  **UAT (Staging)** | A fully dressed rehearsal store — looks real, used for final walkthroughs before opening |
|  **Production** | The actual open store — real customers, real transactions, real consequences |

**Why three?** Because if something breaks in the back room, no customer ever sees it. You test, you rehearse, and only when everyone is confident — you go live.

---

## The Three Instances at a Glance

| |  Development |  UAT |  Production |
|---|---|---|---|
| **What it is** | Internal testing sandbox | Final rehearsal before go-live | The live, real business system |
| **Who uses it** | Internal tech & dev teams | QA teams, stakeholders, clients | Operations staff & end customers |
| **Data inside** | Fake/test data only | Anonymized copies of real data | Live customer data |
| **Safety Level** |  Fully safe to break |  Handle with care |  Extreme caution — always |
| **If something breaks** | No impact | Minimal impact | Direct business impact |
| **Backups** | Ad-hoc (as needed) | Weekly | Daily (automated) |
| **Stability** | May be unstable | Stable and reliable | Always stable, 24/7 monitored |
| **Access** | Internal team only | Authorized testers only | Authorized users & customers |

---

## Instance 1 —  Development

### What Is It?

The Development instance is your **safe experimental space**. It's where new features are built and tested before anyone outside the tech team ever sees them. Nothing here is final, and nothing here affects your real business.

Think of it as a workshop — tools are out, things might be unfinished, and that's perfectly fine.

> **A little technical context:** This environment runs on isolated infrastructure with synthetic (fake) data. It has no connection to your live store's database, so whatever happens here stays here.

### When to Use It

- You're testing a new feature or workflow for the first time
- A developer is fixing a bug and needs to verify the fix works
- You want to explore how the system behaves under a specific scenario
- You're doing an internal proof-of-concept before proposing a change

### Why It Exists

Without a development instance, every test would happen on the live store — putting real customers and real orders at risk. The development instance gives the technical team room to experiment, fail safely, and improve before anything reaches the business.

###  The Golden Rule

> **"Break things freely here — that's what it's for. Just don't share it with clients or use real customer data."**

---

## Instance 2 —  UAT (User Acceptance Testing)

### What Is It?

The UAT instance is your **dress rehearsal environment**. It's set up to look and behave almost exactly like your live store, but it's not live yet. This is where real people — business owners, QA testers, and clients — review changes and give their approval before anything goes public.

Think of it as a preview screening before a film opens to the public.

> **A little technical context:** UAT uses anonymized copies of real production data (names and sensitive details are masked), so testing feels realistic without exposing actual customer information.

### When to Use It

- A new feature has been built and needs sign-off from stakeholders
- QA teams are running structured test cases before release
- You need to verify a bug was actually fixed in a realistic setting
- You're training business users on a new workflow
- A client needs to review and approve something before it goes live
- You're testing how HotWax connects with a third-party system (like a courier or payment provider)

### Why It Exists

The UAT instance is the final checkpoint between testing and the real world. It catches anything the development team may have missed and ensures business stakeholders are confident before the change affects customers.

###  The Golden Rule

> **"Treat this almost like the live store. Test thoroughly, use realistic scenarios, and don't approve anything here that you wouldn't be comfortable putting in front of a real customer."**

---

## Instance 3 —  Production

### What Is It?

The Production instance is **your live store**. Real customers are using it right now. Every order, every inventory update, every transaction happens here. This is the system your business depends on every day.

There is no "undo" button here — every action has a real consequence.

> **A little technical context:** Production runs with the highest level of stability, security, and monitoring. It is backed up daily and watched around the clock to catch any issues before they affect customers.

### When to Use It

- Processing real customer orders
- Checking live inventory levels
- Performing day-to-day operational tasks
- Accessing real business data and reports
- Handling customer service requests that require live system access

### Why It Exists

This is the entire reason the other two instances exist — to protect this one. Everything tested in Development and signed off in UAT eventually makes its way here, but only after it's been verified to be safe.

###  The Golden Rule

> **"This is the live store. Every click matters. Never test here, never experiment here, and always double-check before making any change."**

---

## How to Access Each Instance

Each HotWax app card gives you three access points. Here's where to find them:

| Instance | How to Access | Example URL |
|---|---|---|
|  Development | Click the **bottom-left icon** on the app card | `https://dev-instance.hotwax.io` |
|  UAT | Click the **bottom-right icon** on the app card | `https://demo-maarg-uat.hotwax.io` |
|  Production | Click the **main app card** itself | `https://demo-maarg.hotwax.io` |

---

## Quick Decision Guide

Not sure which instance to use? Ask yourself:

```
Is this a new feature or an experiment?
   → Use Development 

Is this a test that needs stakeholder or client approval?
   → Use UAT 

Is this a real business task with real customers involved?
   → Use Production 
```

---

## Common Mistakes to Avoid

|  Mistake |  What to Do Instead |
|---|---|
| Testing a new feature directly in Production | Always test in Development first, then UAT |
| Sharing the Development URL with a client | Use UAT for any client-facing demos or reviews |
| Using real customer names/emails in Development | Use fake/synthetic data in Development only |
| Skipping UAT and going straight to Production | UAT is a required checkpoint — never skip it |
| Making config changes in Production without approval | Test in UAT, get sign-off, then apply to Production |

---

## Summary

| If you remember nothing else... |
|---|
|  **Development** = Safe to break. Internal only. No real data. |
|  **UAT** = Almost real. For approvals and final checks before go-live. |
|  **Production** = This is real. Real customers. Be careful, always. |

---
