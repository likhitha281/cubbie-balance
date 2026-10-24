# Cubbie Balance

> College shouldn't require choosing between your GPA and having a life.

Cubbie Balance is a student-life planning Skill for Cubbie that helps students decide how to use limited time across academics, jobs, recruiting, recovery, and relationships.

Instead of treating every free hour as another opportunity to study, Balance asks a different question:

**What deserves my time right now — and what can safely wait?**

## Why Cubbie Balance?

Student schedules are more complicated than assignment deadlines.

A student may simultaneously have:

- classes and exams
- assignments and projects
- a part-time job
- internship applications
- coding assessments
- interviews
- career fairs
- research
- friends and family
- basic recovery

Traditional planners mostly answer:

> "When can I fit this task?"

Cubbie Balance tries to answer:

> "Given everything happening in my life, what is actually worth doing?"

## What it uses

When relevant and connected, Cubbie Balance can reason over:

- Canvas assignments, exams, course materials, announcements, and grades
- Google Calendar commitments
- Gmail and synced email events for interviews, assessments, recruiting deadlines, and opportunities
- Cubbie's memory for recurring schedules, preferences, and the student's actual study pace
- the web for relevant outside events and opportunities

The Skill does not require every integration to work. It degrades gracefully when information is unavailable.

## Core interactions

### "Plan my week"

Balance looks across the student's current obligations and separates them into:

**MUST DO** — high-risk or high-value work

**CAN WAIT** — work that can safely move

**PROTECTED** — recovery or social time that does not need to become study time

**WATCH** — an upcoming collision or risk

It then creates a realistic week without filling every open hour.

### "I'm overwhelmed"

Rescue Mode reduces the student's situation to:

**NOW**

**NEXT**

**NOT TODAY**

The goal is to reduce competing priorities rather than create a larger task list.

### "Should I go?"

Students can ask whether they have room for a party, dinner, club event, career fair, workshop, meetup, or other opportunity.

Balance responds with:

**GO**

**GO WITH A CONDITION**

or

**SKIP THIS ONE**

based on actual workload, recoverable time, conflicts, and opportunity value.

Leisure does not need to be "earned" with unrelated productivity.

### "What can I drop?"

When everything does not fit, Balance identifies the smallest cuts that make the week feasible.

It prefers postponing, reducing scope, or dropping low-value flexible work before sacrificing sleep or every meaningful social block.

## Personalization

Cubbie Balance does not assume every student works at the same pace.

If a student consistently needs more time for reading, coding, writing, mathematics, or exam review, future plans can account for that pattern.

The Skill prefers specific observations such as:

> "This course's readings usually take longer than expected."

rather than labeling a student a "slow learner."

## Example

A student asks:

> My friends want me to go out Friday from 7–11 PM. Should I go?

After considering the student's coursework and schedule, Cubbie Balance can determine whether the time is actually recoverable instead of automatically telling the student to study.

The purpose is not to maximize productivity.

Sometimes the correct recommendation is:

> **Go. You have enough time.**

And sometimes it is:

> **Skip this one. The lost study time cannot realistically be recovered before tomorrow's exam.**

## Design principles

1. A free hour is not automatically a study hour.
2. Deadlines are constraints, not automatic priorities.
3. Expiring opportunities matter.
4. Different students require different amounts of time.
5. Recovery and relationships are legitimate uses of time.
6. When everything cannot fit, something should be intentionally deprioritized.
7. Important external actions require student confirmation.
8. Private context should remain private.

## Privacy

Balance may reason using sensitive personal context such as grades, email contents, calendar details, and workload.

That information should not be unnecessarily exposed.

This becomes particularly important in the next phase of the project: agent-to-agent coordination.

## Track 2 direction

Track 1 asks:

> **How should one student allocate their limited time?**

Track 2 asks:

> **How can several students coordinate their limited time without revealing their private lives to each other?**

The planned multi-agent system allows each student's Balance agent to privately evaluate proposed meeting or social times.

Instead of sharing grades, assignment names, emails, or reasons for being unavailable, an agent can expose derived coordination information such as:

- feasible / infeasible
- flexibility
- preference strength
- private opportunity cost: low / medium / high

Agents can then negotiate a shared plan before asking their students for final approval.

## Example Track 2 concept

Three friends want to meet this weekend.

One student's agent privately knows they have an exam.

Another knows its student has a work shift.

A third knows its student has an important project deadline.

The agents do not reveal those details to one another.

They negotiate using minimal derived constraints and propose the option that best respects everyone's private commitments.

## Repository

`SKILL.md` contains the Cubbie Balance behavior and instructions.

`examples/` contains demonstration interactions.

`tests/` contains behavioral scenarios used to evaluate the Skill.

## Status

Track 1 is under active hackathon testing with real Cubbie interactions.

Built for the Cubbie Skill Hackathon.