# Cubbie Balance — Track 1 Demo

This document contains the planned Track 1 demo flow and results observed while testing the installed Cubbie Balance Skill with connected student context.

## Demo Flow

### Opening

**Student**

> Plan my week. I want to improve my grades, but I work part-time and I feel like studying takes over my social life.

**Expected behavior**

Cubbie gathers relevant connected Canvas, Calendar, Gmail/email-event, and remembered preference context.

It produces a concise whole-life plan with:

- MUST DO
- CAN WAIT
- PROTECTED
- WATCH

rather than filling every free hour.

### Follow-up: Social Decision

**Student**

> My friends invited me out Friday from 7 to 10. Should I go?

**Expected behavior**

Cubbie checks:

- conflicts
- remaining academic/career work
- recoverable future time
- recent balance

It answers:

- GO
- GO WITH A CONDITION
- SKIP THIS ONE

and briefly explains why.

### Follow-up: Overload

**Student**

> Actually I also got a coding assessment email and it expires tomorrow. I'm overwhelmed.

**Expected behavior**

Cubbie enters Rescue Mode and returns:

- NOW
- NEXT
- NOT TODAY

The expiring assessment should receive appropriate opportunity-loss weight rather than blindly prioritizing Canvas.

### Follow-up: Action

**Student**

> Okay, remind me to start the assessment tonight.

**Expected behavior**

Cubbie confirms the proposed reminder time if it is not already clear, then creates it using its reminder ability.

---

# Validated Results

The core Cubbie Balance flows were manually tested using the installed Skill and connected student context.

## 1. Plan My Week — PASS

### Student

> Plan my week. I want to improve my grades, but I work part-time and I feel like studying takes over my social life.

### Initial degraded-mode behavior

During the first test, Canvas was still completing its initial sync.

Cubbie explicitly acknowledged this rather than inventing Canvas information.

It created a provisional plan containing:

- MUST DO
- CAN WAIT
- PROTECTED
- WATCH

and protected sleep, meals, social/recovery time, and buffer time.

This validated graceful behavior when an important source was temporarily incomplete.

### Full-context behavior

After Canvas became available, Cubbie checked Canvas, calendars, and relevant recruiting emails.

It identified:

- CSE 598 Memory as an important upcoming academic priority
- the execution-flow portion of the CSE 598 work as particularly important
- an AWS Arizona Public Sector AI Innovation Day as a time-sensitive career opportunity
- APM 527 HW3 as work that could safely wait
- CSE 543 practice as useful academic preparation
- Wednesday and Friday evenings as protected social time
- Thursday evening as recovery time

It also avoided stacking additional recruiting activities on top of the AWS event.

Cubbie detected that work shifts and some recurring class information were still missing instead of inventing those commitments.

### Finding

The Skill successfully combined academic, career, scheduling, and social/recovery considerations rather than acting as a Canvas deadline viewer.

---

## 2. Should I Go? — PASS

### Student

> My friends want me to go out Friday from 7 PM to 11 PM. Should I go?

### Observed response

> Go—with one condition: finish Friday’s 45-minute APM review and confirm your CSE 543 team has no urgent deliverable before heading out.
>
> Friday, Oct 30, 7–11 PM fits the social evening we protected, and the known Canvas deadlines are Nov 4 and Nov 16. You don’t need to earn the night by studying all day. Does it clash with a work shift or an early Saturday start?

### Finding

The Skill evaluated the social activity against real academic context and recoverable time instead of automatically recommending additional studying.

Testing also exposed an important refinement:

Leisure should not receive an unrelated productivity condition merely to make it feel earned.

GO WITH A CONDITION should be used only when the condition materially changes whether attending is safe.

---

## 3. Rescue Mode — PASS

### Student

> I'm overwhelmed. I don't think I can do everything this week. What should I focus on right now?

### Observed response

> NOW: Spend 20 minutes on CSE 598 Memory: pick one execution path and note what you need to trace. Don’t write the whole report. It’s due Nov 4, and execution flow is worth 35 points.
>
> NEXT: Check your CSE 543 team’s next deliverable before adding more work.
>
> NOT TODAY: Optional recruiting sessions, IA/grader application prep, and polishing notes. APM HW3 can wait today; it’s due Nov 16.
>
> Stop after that first 20-minute block and take a break. Want a check-in in 30 minutes?

### Finding

Rescue Mode reduced the student's number of competing priorities instead of generating another large task list.

It:

- selected one bounded immediate action
- identified one next uncertainty
- explicitly removed several tasks from the current day
- gave the student a stopping point
- asked before creating a check-in

---

## 4. What Can I Drop? — PASS

### Student

> What can I drop this week? I don't have enough time for everything.

### Observed response

> Cut the optional extras, not all your downtime.
>
> • Drop extra recruiting sessions. You already registered for Thursday’s AWS event; don’t stack more on top.
>
> • Postpone IA/grader application prep if interested—it has a Nov 7 priority deadline.
>
> • Defer finishing APM HW3 until next week; it’s due Nov 16.
>
> • Skip rewriting notes and polishing beyond the rubric.
>
> Keep CSE 598 Memory progress and check your CSE 543 team’s next deliverable. Don’t cut paid shifts, required classes, or sleep. Keep Friday’s outing if those obligations fit.
>
> Which work shifts are taking up your week?

### Finding

The Skill actually removed work.

It prioritized dropping or postponing:

- extra recruiting
- non-urgent application preparation
- distant coursework
- unnecessary polishing

before sacrificing:

- paid work
- required classes
- sleep
- feasible social time

---

## 5. Reminder Action — PASS

### Student

> Remind me tonight at 7 PM to work on CSE 598 Memory for 20 minutes.

### Observed response

> Set for tonight at 7 PM, Arizona time: work on CSE 598 Memory for 20 minutes, then take a break.

### Finding

The Skill successfully moved from planning to action using Cubbie's reminder capability.

Because the student supplied an exact action and time, Cubbie did not ask unnecessary clarification questions.

---

# Track 1 Validation Summary

| Capability | Result |
|---|---|
| Whole-week planning | PASS |
| Canvas context | PASS |
| Calendar context | PASS |
| Gmail/recruiting context | PASS |
| Missing-data fallback | PASS |
| Academic prioritization | PASS |
| Career opportunity reasoning | PASS |
| Protected social/recovery time | PASS |
| Should I Go? | PASS |
| Rescue Mode | PASS |
| What Can I Drop? | PASS |
| Reminder action | PASS |
| Consent-aware actions | PASS |
| Avoids filling every free hour | PASS |

## Key Product Finding

The strongest behavior observed during testing was not simply generating a better schedule.

Cubbie Balance could use real student context to decide:

- what deserves attention
- what can wait
- what should be dropped
- when an opportunity is worth protecting
- when social time is genuinely safe

The goal is not maximum productivity.

**A free hour is not automatically a study hour.**