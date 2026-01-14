# Team Design Principles

> **Last Updated:** January 2026 | **Version:** 2.0

## Table of Contents
1. [Introduction](#introduction)
2. [The Five Core Principles](#the-five-core-principles)
   - [1. Cross-Functional Teams](#1-cross-functional-teams)
   - [2. Dunbar's Law](#2-dunbars-law)
   - [3. Team Ownership](#3-teams-should-own-their-software)
   - [4. Cognitive Load Management](#4-cognitive-load)
   - [5. Tuckman's Team Performance Model](#5-tuckmans-team-performance-model)
3. [Implementation Guide](#implementation-guide)
4. [Common Challenges & Solutions](#common-challenges--solutions)
5. [Assessment Checklists](#assessment-checklists)
6. [Glossary](#glossary)
7. [References](#references)

---

## Introduction

### Purpose
This document outlines the fundamental principles for designing and maintaining high-performing software development teams. These principles are based on research in cognitive psychology, organizational behavior, and decades of industry experience.

### Core Philosophy
**Our teams should be designed so that they are small, long-lived, cross-functional units that own their work end-to-end.**

### Why These Principles Matter
- **Faster Delivery**: Autonomous teams make decisions quickly without bureaucratic overhead
- **Higher Quality**: Teams that own their work take pride in craftsmanship and quality
- **Better Retention**: Clear ownership and autonomy increase job satisfaction
- **Reduced Complexity**: Proper team design reduces cognitive load and communication overhead
- **Sustainable Pace**: Right-sized teams with clear boundaries prevent burnout

---

## The Five Core Principles

## 1. Cross-Functional Teams

### Principle
**All teams should be cross-functional, equipped with the diverse skill sets necessary to tackle their assigned problems independently.**

### Why It Matters
Cross-functional teams reduce dependencies on external teams, enabling faster delivery cycles and greater autonomy. When a team has all the skills needed to complete their work, they can move from idea to production without handoffs or waiting.

### Key Characteristics
- ✅ Team has all skills needed to deliver end-to-end (design, development, testing, deployment, operations)
- ✅ Minimal dependencies on external teams for day-to-day work
- ✅ Can make decisions and execute without constant external approval
- ✅ Shares collective responsibility for outcomes, not just individual tasks

### Anti-Patterns to Avoid
- ❌ Siloed teams organized by function (e.g., separate "frontend team," "backend team," "QA team")
- ❌ Teams that constantly wait for other teams to complete work
- ❌ Over-specialization where only one person can do critical tasks
- ❌ "Throw it over the wall" mentality between disciplines

### Practical Example
**Good**: A product team consisting of 2 backend engineers, 1 frontend engineer, 1 designer, and 1 QA engineer who together own the entire checkout experience.

**Bad**: A backend team builds APIs, then hands off to a frontend team, who then hands off to a QA team for testing.

---

## 2. Dunbar's Law

### What Is Dunbar's Number?
Dunbar's number is a **cognitive limit** to the number of people with whom an individual can maintain **stable social relationships**. It refers to the maximum number of people a person can truly know and relate to in a meaningful way.

The original research by anthropologist Robin Dunbar suggests:
- **5 people**: Close personal friends
- **15 people**: Good friends
- **50 people**: Friends/regular social contacts
- **150 people**: Meaningful contacts (Dunbar's number)

### How Does It Relate to Building Teams?

#### Team Size Guidelines
- **A single team should be between 5 and 8 people** (based on industry experience)
  - *Note: In a high-trust organization, it can be increased to no more than 15 people*
- **A domain, service area, or grouping of teams should be no more than 50 people**
  - *Note: In a high-trust organization, it can be increased to no more than 150 people*

#### Why These Numbers Matter
- **Communication Complexity**: As team size grows, communication paths increase exponentially. A team of 5 has 10 communication paths; a team of 8 has 28; a team of 15 has 105.
- **Trust & Cohesion**: Smaller teams build trust faster and maintain it more easily
- **Decision-Making**: Smaller teams reach consensus faster
- **Coordination Overhead**: Larger teams spend disproportionate time on coordination

### What Is a "High-Trust Organization"?
A high-trust organization exhibits:
- ✅ Transparent decision-making processes
- ✅ Psychological safety to voice concerns and make mistakes
- ✅ Clear, consistent values lived by leadership
- ✅ Empowered teams with autonomy to make decisions
- ✅ Open communication across all levels
- ✅ Track record of supporting teams when things go wrong

> **Key Takeaway**: To reduce cognitive load and create a high-trust environment, we should design our teams with Dunbar's Law in mind.

---

## 3. Teams Should Own Their Software

### The Ownership Principle
**Teams should take ownership of their system or subsystem within a domain, considering both the team's cognitive load and the complexity of the specific area they are tasked with managing.**

### Why Ownership Matters

#### Responsibility
- When a team owns its software, it takes collective responsibility for its creation, maintenance, and improvement
- This shared ownership fosters a sense of pride and accountability
- Teams think long-term rather than optimizing for short-term delivery

#### Faster Iterations
- Ownership enables teams to iterate quickly without bureaucratic delays
- Teams can adapt to changing requirements, fix bugs, and enhance features promptly
- No waiting for other teams to prioritize your bug fixes or improvements

#### Deep Understanding
- Owning software means understanding it inside out
- Teams gain insights into architecture, code quality, and user needs
- This knowledge compounds over time, making the team increasingly effective

#### Quality and Craftsmanship
- Ownership encourages craftsmanship through clean code, robust testing, and thoughtful design
- Teams take pride in delivering high-quality software
- "You build it, you run it" mentality drives quality at the source

#### Empowerment and Autonomy
- Empowered teams make better decisions aligned with business goals and user needs
- Autonomy drives creativity and innovation
- Teams can experiment and learn without excessive oversight

### What Teams Should Own
- **Code**: Complete ownership of codebase for their domain
- **Architecture**: Decision-making authority for technical architecture within their domain
- **Quality**: Responsibility for testing, monitoring, and reliability
- **Operations**: Deployment, monitoring, incident response, and on-call rotation
- **Product Decisions**: Partnership with product management on prioritization and scope
- **Documentation**: Maintaining clear documentation for their services

### Anti-Patterns to Avoid
- ❌ Separate "ops team" that handles all deployments
- ❌ Handing off maintenance to a different team after launch
- ❌ Shared ownership where "everyone owns it" (which means no one owns it)
- ❌ Temporary project teams that disband after launch

### Practical Example
**Good**: The Payments team owns the payment processing service, including code, infrastructure, monitoring, on-call rotation, and product decisions about payment features. They respond to incidents and iterate on improvements continuously.

**Bad**: A project team builds the payment service, then hands it to an operations team for deployment and a maintenance team for ongoing support.

---

## 4. Cognitive Load

### What Is Cognitive Load?
In cognitive psychology, cognitive load represents the **mental effort** required for various tasks and activities. It encompasses any mental process, from memory and perception to language, as each of these processes consumes energy and effort.

### The Three Types of Cognitive Load

#### 1. Intrinsic Cognitive Load
- **Definition**: The inherent complexity or difficulty associated with a specific task or information
- **Examples**:
  - What is the structure of a Java class? How do I create a new method?
  - Understanding core programming concepts, algorithms, or business domain logic
- **Management Strategy**: Can only be reduced through better learning and skill development

#### 2. Extraneous Cognitive Load
- **Definition**: The effort imposed by the environment or the way information and tasks are presented
- **Examples**:
  - How do I deploy this component? How do I configure this service?
  - Complex tooling, poor documentation, inconsistent processes
  - Context switching between many services, tools, or systems
- **Management Strategy**: This is where we have the most opportunity to improve through better tools, processes, and platform engineering

#### 3. Germane Cognitive Load
- **Definition**: The effort needed to convert new information into stable, long-term learning (schema formation)
- **Examples**:
  - How should this service interact with ABC service?
  - Understanding system architecture, design patterns, and trade-offs
- **Management Strategy**: Supported through good documentation, knowledge sharing, and mentorship

### Why Cognitive Load Matters for Teams
- **Capacity**: Every team has a finite cognitive capacity
- **Bottlenecks**: Exceeding cognitive capacity leads to errors, delays, and burnout
- **Ownership Scope**: Teams should own systems that fit within their cognitive capacity
- **Tooling Overhead**: Complex toolchains and processes steal capacity from valuable work

### Strategies to Reduce Cognitive Load

#### Reduce Extraneous Load
- ✅ Standardize tools and processes across the organization
- ✅ Create self-service platforms with excellent developer experience
- ✅ Invest in automation (CI/CD, testing, deployments)
- ✅ Provide clear, up-to-date documentation
- ✅ Reduce the number of services/systems a team must understand

#### Support Germane Load
- ✅ Create clear architectural diagrams and documentation
- ✅ Establish regular knowledge sharing sessions
- ✅ Pair programming and mentorship programs
- ✅ Document architectural decision records (ADRs)

#### Right-Size Ownership
- ✅ Don't assign too many services/domains to one team
- ✅ Split teams or services when cognitive load becomes too high
- ✅ Consider team maturity and experience when assigning ownership

> **Key Takeaway**: When designing teams, it's essential to consider the cognitive load placed on them, understand its components, and implement strategies to minimize it.

### Warning Signs of Excessive Cognitive Load
- 🚨 Team frequently misses deadlines or commitments
- 🚨 High error rates or production incidents
- 🚨 Team members report feeling overwhelmed
- 🚨 Knowledge concentrated in one or two people
- 🚨 Constant context switching between unrelated systems
- 🚨 Difficulty onboarding new team members

---

## 5. Tuckman's Team Performance Model

### What Is Tuckman's Team Performance Model?
**Tuckman's Team Performance Model** (also known as Tuckman's stages of group development) is a theory proposed by **Bruce Tuckman** in 1965 that outlines the stages of team development. Understanding these stages helps leaders foster collaboration, manage conflicts, and optimize team performance.

### The Five Stages

#### 1. Forming
- In this initial phase, team members come together, often with excitement but also caution
- Relationships and trust are built from scratch
- Discussion tends to be polite, with team members focused on getting to know each other
- **Duration**: Typically 2-4 weeks
- **Leadership Focus**: Provide clear direction, establish norms, facilitate introductions

#### 2. Storming
- Conflict emerges as team members establish their positions and boundaries
- Friction arises due to differing opinions and approaches
- Effective leadership during this phase is crucial to navigate conflicts
- **Duration**: Can last weeks to months depending on team maturity
- **Leadership Focus**: Facilitate healthy conflict resolution, establish decision-making processes

#### 3. Norming
- Once initial conflicts are resolved, the team begins to collaborate effectively
- Trust deepens, and team members learn how to work together harmoniously
- The focus shifts from individual differences to collective goals
- **Duration**: Ongoing as team stabilizes
- **Leadership Focus**: Reinforce positive behaviors, celebrate wins, codify working agreements

#### 4. Performing
- High efficiency is achieved during this stage
- The team operates smoothly, leveraging its combined abilities
- Productivity and collaboration are at their peak
- **Duration**: This is the desired steady state
- **Leadership Focus**: Empower the team, remove blockers, focus on strategic challenges

#### 5. Adjourning
- This final stage occurs when a project concludes or team disbands
- Tasks are wrapped up, achievements celebrated, and team members may part ways or transition to new projects
- **Duration**: Planned transitions over several weeks
- **Leadership Focus**: Celebrate achievements, conduct retrospectives, facilitate knowledge transfer

### Why This Matters for Team Design

> **Key Takeaway**: Whenever feasible, a team should take ownership of a single system or subsystem and remain stable over time. Avoid frequent team restructures that reset teams back to the Forming stage.

#### Implications
- **Keep Teams Stable**: Each reorganization resets teams to Forming, destroying accumulated trust and efficiency
- **Performance Takes Time**: It can take 3-6 months for a new team to reach Performing stage
- **Cost of Reorganization**: Frequent reorgs have a massive productivity cost
- **Plan for Adjourning**: When teams must disband, do it thoughtfully with proper knowledge transfer

#### When Team Changes Are Necessary
Sometimes team changes are unavoidable:
- Business priorities shift dramatically
- Team size needs adjustment due to growth or attrition
- Cognitive load assessment indicates restructuring is needed

When making changes:
1. ✅ Minimize disruption - change as few teams as possible
2. ✅ Preserve team cores - keep subsets of teams together
3. ✅ Allow time for re-forming - don't expect immediate performance
4. ✅ Provide support - facilitate team building activities
5. ✅ Communicate clearly - explain the "why" behind changes

---

**Document Version:** 2.0
**Last Updated:** January 2026