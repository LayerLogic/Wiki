# New Software Engineer — Onboarding Plan

> **Welcome to LayerLogic!** This guide will walk you through your first week, from environment setup to your first contribution. By the end of Day 5, you'll be productive and ready to take on your first change request.

---

## Quick Reference

| Item                      | Details                                                                           |
| ------------------------- | --------------------------------------------------------------------------------- |
| **Your buddy**            | Mohammed Agha — [mohammed.agha@layerlogic.se](mailto:mohammed.agha@layerlogic.se) |
| **Onboarding duration**   | 5 working days (1 week)                                                           |
| **Team size**             | 2–3 engineers                                                                     |
| **Primary communication** | Microsoft Teams                                                                   |
| **Project management**    | Jira                                                                              |
| **Source control**        | GitHub                                                                            |
| **Design**                | Figma                                                                             |

> 💡 **Rule of thumb:** If you're stuck on anything for more than 20 minutes, reach out to your buddy. We're a small team — asking questions is faster and encouraged.

---

## Before Your First Day

Your buddy will prepare the following before you arrive:

- [ ] GitHub organisation invitation sent
- [ ] Jira workspace access granted
- [ ] Microsoft Teams added to relevant channels
- [ ] Figma team invitation sent
- [ ] AWS IAM account created (ask your buddy for credentials)

---

## Day 1 — Environment Setup & Company Orientation

> **Goal:** Laptop configured, tools installed, all accounts accessible, and a general understanding of LayerLogic.

### Morning: Accounts & Access

- [ ] Accept GitHub organisation invitation and verify access to all repositories
- [ ] Log in to Jira and familiarise yourself with the project board(s)
- [ ] Log in to Microsoft Teams and introduce yourself in the team channel
- [ ] Log in to Figma and locate the current design files
- [ ] Log in to the AWS Console — confirm you can access the relevant services
- [ ] Bookmark all key URLs:

| Tool        | URL                                                              |
| ----------- | ---------------------------------------------------------------- |
| GitHub      | _Your buddy will provide_                                        |
| Jira        | _Your buddy will provide_                                        |
| Figma       | _Your buddy will provide_                                        |
| AWS Console | [https://console.aws.amazon.com](https://console.aws.amazon.com) |
| This Wiki   | _Link to this repository_                                        |

### Afternoon: Development Environment

#### 1. Install Core Tools

```bash
# Node.js (use nvm for version management)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install --lts
nvm use --lts

# Verify installation
node --version   # Should be at least 20.x
npm --version

# Docker Desktop
# Download from https://www.docker.com/products/docker-desktop/

# Git (should be pre-installed on macOS)
git --version
```

#### 2. Configure Git

```bash
# Set your identity
git config --global user.name "Your Full Name"
git config --global user.email "your.email@layerlogic.se"

# Set default branch name
git config --global init.defaultBranch main

# Set up signed commits (recommended)
# See: https://docs.github.com/en/authentication/managing-commit-signature-verification
```

#### 3. Clone Repositories

```bash
# Clone the wiki
git clone <wiki-repo-url>

# Clone the main project(s) — your buddy will tell you which ones
git clone <project-repo-url>

# Install dependencies
cd <project-directory>
npm install
```

#### 4. IDE Setup

We recommend **Visual Studio Code** with these extensions:

| Extension                          | Purpose                       |
| ---------------------------------- | ----------------------------- |
| ESLint                             | JavaScript/TypeScript linting |
| Prettier                           | Code formatting               |
| Docker                             | Container management          |
| GitLens                            | Git history & blame           |
| MongoDB for VS Code                | Database exploration          |
| Volar                              | Vue.js support                |
| Arduino (if working with hardware) | Arduino development           |

#### 5. Verify Local Environment

```bash
# Start the development server
npm run dev

# Run tests
npm test

# Start Docker containers (if applicable)
docker compose up -d
```

- [ ] **Checkpoint:** Can you run the project locally and see it in the browser?

### End of Day 1: Buddy Check-in (15 min)

Walk through what you've set up. Flag any issues. Your buddy will answer questions and confirm you're ready for Day 2.

---

## Day 2 — Codebase Orientation & SDLC Process

> **Goal:** Understand the project architecture, tech stack, and how LayerLogic builds software.

### Morning: Tech Stack Deep Dive

Read and understand the current technology choices:

| Layer                | Technology                           | Notes                                                                              |
| -------------------- | ------------------------------------ | ---------------------------------------------------------------------------------- |
| **Frontend**         | React.js / Vue.js                    | Some projects use React, others Vue — ask your buddy which applies to your project |
| **Backend**          | Node.js + Express.js                 | REST APIs                                                                          |
| **Database**         | MongoDB                              | Mongoose ODM                                                                       |
| **Infrastructure**   | AWS                                  | EC2, S3, Lambda, etc. — ask your buddy for specifics                               |
| **Containerisation** | Docker                               | Local dev and deployment                                                           |
| **Language**         | JavaScript (migrating to TypeScript) | New code should be written in TypeScript where possible                            |

#### Codebase Walkthrough

Your buddy will walk you through:

- [ ] Project folder structure
- [ ] How the frontend communicates with the backend
- [ ] Database models and schemas
- [ ] Docker setup (`docker-compose.yml`, Dockerfiles)
- [ ] Environment variables (`.env` files — never commit secrets!)
- [ ] Deployment pipeline and AWS architecture

> 📝 **Take notes!** Write down anything that isn't obvious from the code. If it's worth knowing, it's worth documenting.

### Afternoon: SDLC Process

Read through the LayerLogic SDLC Wiki — this is how we build software:

| Priority        | Document                                                                  | Time   |
| --------------- | ------------------------------------------------------------------------- | ------ |
| 🔴 Must read    | [README (SDLC Overview)](../README.md)                                    | 10 min |
| 🔴 Must read    | [Creating Pull Requests](../issue_activities/creating_pull_requests.md)   | 10 min |
| 🔴 Must read    | [Reviewing Pull Requests](../issue_activities/reviewing_pull_requests.md) | 10 min |
| 🔴 Must read    | [Implementation](../issue_activities/implementation.md)                   | 10 min |
| 🟡 Should read  | [Requirements Analysis](../issue_activities/requirements_analysis.md)     | 10 min |
| 🟡 Should read  | [Design Specifications](../issue_activities/design_specifications.md)     | 10 min |
| 🟡 Should read  | [Writing Tests](../issue_activities/writing_tests.md)                     | 10 min |
| 🟡 Should read  | [Problem Resolution](../issue_activities/problem_resolution.md)           | 5 min  |
| 🟢 Good to know | [Sprint Planning](../sprint_activities/sprint_planning.md)                | 5 min  |
| 🟢 Good to know | [Risk Analysis](../issue_activities/risk_analysis.md)                     | 5 min  |
| 🟢 Good to know | [Definitions & Glossary](../data/definitions.md)                          | 5 min  |

**Key takeaways to remember:**

1. **All work ties to a change request** (GitHub/Jira issue)
2. **Branch naming:** `<issue-number>-short-description`
3. **Commit messages** must reference the issue number
4. **Every PR gets reviewed** before merging
5. **Tests are expected** for new functionality

### End of Day 2: Buddy Check-in (15 min)

Discuss the codebase walkthrough. Ask any questions about the SDLC process. Your buddy will confirm you understand the workflow.

---

## Day 3 — First Contribution (Guided)

> **Goal:** Complete your first end-to-end contribution following the SDLC process.

### Morning: Your First Change Request

Your buddy will assign you a **starter task** — a small, low-risk change request designed for onboarding. Good examples:

- Fix a typo or improve documentation
- Add a small UI improvement
- Write a missing unit test
- Fix a minor bug

**Follow the full workflow:**

1. [ ] **Find your assigned issue** in Jira/GitHub
2. [ ] **Create a branch** from `main`:
   ```bash
   git checkout main
   git pull origin main
   git checkout -b <issue-number>-short-description
   ```
3. [ ] **Make your changes** — follow the coding standards
4. [ ] **Write or update tests** if applicable
5. [ ] **Commit with a proper message:**

   ```bash
   git add .
   git commit -m "Short description of the change

   Detailed explanation of what and why.

   Issue #<number>"
   ```

6. [ ] **Push and create a PR:**
   ```bash
   git push -u origin <branch-name>
   ```
7. [ ] **Fill in the PR template** — check off the relevant activities
8. [ ] **Assign your buddy as reviewer**

### Afternoon: Code Review Experience

- [ ] Your buddy reviews your PR and provides feedback
- [ ] Address any comments (follow the [Reviewing Pull Requests](../issue_activities/reviewing_pull_requests.md) guide)
- [ ] Merge your PR once approved 🎉

> 🎯 **Milestone:** You've completed your first full SDLC cycle — from issue to merged code!

### End of Day 3: Buddy Check-in (15 min)

Retrospective on your first contribution. What felt natural? What was confusing? Your buddy will help clarify.

---

## Day 4 — Domain Knowledge & Hardware

> **Goal:** Understand LayerLogic's domain, hardware setup, and how software interfaces with physical devices.

### Morning: Domain & Hardware Orientation

LayerLogic's software interfaces with hardware — understanding this connection is essential.

**Session with Mohammed or Andre:**

- [ ] Overview of the hardware architecture (Arduino boards, sensors, actuators)
- [ ] How the software communicates with hardware (serial communication, protocols)
- [ ] Walk through the hardware setup in the office/lab
- [ ] Review any hardware-related code in the codebase

**Key concepts to understand:**

| Concept                  | Details                                                        |
| ------------------------ | -------------------------------------------------------------- |
| **Arduino**              | Microcontroller platform used for hardware control             |
| **Serial communication** | How the software sends/receives data to/from hardware          |
| **Sensor data**          | What data the hardware collects and how it's processed         |
| **Hardware states**      | How the software handles connection, disconnection, and errors |

> 📚 **Resources for self-study (if needed):**
>
> - [Arduino Getting Started](https://www.arduino.cc/en/Guide)
> - [Serial Communication basics](https://learn.sparkfun.com/tutorials/serial-communication)
> - [Web Serial API (if applicable)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API)

### Afternoon: AWS & Deployment

Your buddy walks you through:

- [ ] AWS services used by the project (EC2, S3, Lambda, etc.)
- [ ] How deployments work (CI/CD pipeline, Docker, staging vs. production)
- [ ] How to access logs and monitoring
- [ ] How to access the staging environment
- [ ] MongoDB Atlas or RDS database access

**Practice:**

- [ ] SSH into a staging server (if applicable)
- [ ] View application logs
- [ ] Access MongoDB and run a simple query

### End of Day 4: Buddy Check-in (15 min)

Review hardware and infrastructure understanding. Discuss any gaps.

---

## Day 5 — Independence & Second Contribution

> **Goal:** Take on a real task independently and solidify your workflow.

### Morning: Second Change Request (Independent)

Your buddy assigns a **slightly more substantial task** — something that involves actual feature work or a meaningful bug fix.

This time, work **independently**:

- [ ] Read the issue description and requirements carefully
- [ ] Plan your approach before coding (discuss with your buddy if unsure)
- [ ] Implement the change following the SDLC activities
- [ ] Write tests
- [ ] Create a PR with a thorough description

### Afternoon: Wrap-up & Going Forward

- [ ] Submit your PR for review
- [ ] While waiting for review, explore areas of the codebase you haven't seen yet
- [ ] Update your local notes / personal documentation

### End of Week: Onboarding Retrospective (30 min)

Sit down with your buddy for a wrap-up conversation:

| Topic                   | Discussion Points                                         |
| ----------------------- | --------------------------------------------------------- |
| **What went well?**     | What parts of onboarding were most helpful?               |
| **What was confusing?** | Where did you get stuck? How can we improve?              |
| **Knowledge gaps**      | What areas do you need to study further?                  |
| **Onboarding feedback** | Suggestions for improving this guide for future engineers |
| **Goals for week 2**    | What will you focus on next week?                         |

---

## After Onboarding: Continuing Development

### Week 2–4 Goals

- [ ] Complete 2–3 more change requests of increasing complexity
- [ ] Participate in your first [Sprint Planning](../sprint_activities/sprint_planning.md) meeting
- [ ] Perform your first [Pull Request Review](../issue_activities/reviewing_pull_requests.md) for a teammate
- [ ] Deepen your understanding of the areas most relevant to your work
- [ ] Read through the remaining SDLC documents you haven't reviewed yet

### Ongoing Learning Resources

| Topic          | Resource                                                                                             |
| -------------- | ---------------------------------------------------------------------------------------------------- |
| **TypeScript** | [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/) — we're migrating from JS to TS |
| **Express.js** | [Express.js Guide](https://expressjs.com/en/guide/routing.html)                                      |
| **MongoDB**    | [MongoDB University](https://university.mongodb.com/) — free courses                                 |
| **AWS**        | [AWS Free Training](https://aws.amazon.com/training/digital/)                                        |
| **React**      | [React Documentation](https://react.dev/learn)                                                       |
| **Vue.js**     | [Vue.js Guide](https://vuejs.org/guide/introduction.html)                                            |
| **Docker**     | [Docker Getting Started](https://docs.docker.com/get-started/)                                       |
| **Arduino**    | [Arduino Tutorials](https://www.arduino.cc/en/Tutorial/HomePage)                                     |

---

## Onboarding Checklist — Summary

Use this as a single checklist to track your progress:

### Day 1 — Environment Setup

- [ ] All accounts accessible (GitHub, Jira, Teams, Figma, AWS)
- [ ] Node.js, npm, Docker, Git installed and configured
- [ ] Repositories cloned
- [ ] IDE set up with recommended extensions
- [ ] Project runs locally
- [ ] Buddy check-in completed

### Day 2 — Codebase & Process

- [ ] Tech stack walkthrough completed with buddy
- [ ] Codebase architecture understood (frontend, backend, database)
- [ ] Docker setup understood
- [ ] SDLC Wiki documents read (at least the 🔴 must-reads)
- [ ] Understand the PR workflow end-to-end
- [ ] Buddy check-in completed

### Day 3 — First Contribution

- [ ] Starter task assigned
- [ ] Branch created, changes made, tests written
- [ ] PR created following the template
- [ ] PR reviewed and feedback addressed
- [ ] PR merged
- [ ] Buddy check-in completed

### Day 4 — Domain & Infrastructure

- [ ] Arduino / hardware orientation with Mohammed or Andre
- [ ] Serial communication concepts understood
- [ ] AWS services walkthrough completed
- [ ] Deployment pipeline understood
- [ ] Database access verified
- [ ] Buddy check-in completed

### Day 5 — Independence

- [ ] Second change request completed independently
- [ ] PR submitted with thorough description
- [ ] Onboarding retrospective completed
- [ ] Week 2 goals agreed upon
- [ ] Onboarding feedback provided

---

## Questions?

Don't hesitate to reach out:

| Person            | Contact                                                           | Ask about                    |
| ----------------- | ----------------------------------------------------------------- | ---------------------------- |
| **Mohammed Agha** | [mohammed.agha@layerlogic.se](mailto:mohammed.agha@layerlogic.se) | Anything — he's your buddy!  |
| **Andre**         | _Ask Mohammed_                                                    | Hardware, sensors, Customers |

---

_Welcome aboard! We're glad to have you on the team. 🚀_
