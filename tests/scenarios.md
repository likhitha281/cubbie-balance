# Cubbie Balance Behavioral Test Scenarios

These scenarios test whether Cubbie Balance follows its core product principles.

## Test 1 — Whole-week planning

Prompt:

> Plan my week. I want to improve my grades, but I work part-time and I feel like studying takes over my social life.

Expected:

- checks relevant connected context
- identifies high-risk academic work
- considers work and recruiting commitments
- identifies work that can wait
- protects reasonable recovery/social time
- does not fill every available hour
- communicates missing information instead of inventing it

Pass if the response contains meaningful prioritization rather than only a generic schedule.

## Test 2 — Safe social opportunity

Prompt:

> My friends want me to go out Friday from 7 PM to 11 PM. Should I go?

Expected:

- evaluates real workload and conflicts
- considers recoverable future time
- returns GO, GO WITH A CONDITION, or SKIP THIS ONE
- explains the tradeoff
- does not require unrelated productivity merely to make leisure feel earned

## Test 3 — Unsafe social opportunity

Setup:

The student has an important exam or deadline the next morning and insufficient remaining time to prepare.

Prompt:

> My friends want me to go out tonight. Should I go?

Expected:

- identifies unrecoverable academic risk
- recommends SKIP THIS ONE when appropriate
- explains why without guilt or moralizing

## Test 4 — Rescue Mode

Prompt:

> I'm overwhelmed. I don't think I can do everything this week. What should I focus on right now?

Expected:

- NOW contains one bounded action
- NEXT contains the next meaningful priority
- NOT TODAY explicitly removes work
- does not produce a giant task list
- provides a reasonable stopping point when possible

## Test 5 — Expiring career opportunity

Setup:

A coding assessment expires tomorrow while an assignment is due several days later.

Prompt:

> I have a coding assessment that expires tomorrow, but I also have an assignment due later this week. What should I prioritize?

Expected:

- considers opportunity loss
- does not blindly prioritize Canvas because it is academic
- gives the expiring assessment appropriate priority when the later assignment remains recoverable

## Test 6 — What can I drop?

Prompt:

> What can I drop this week? I don't have enough time for everything.

Expected:

- removes or postpones low-value flexible work
- explains what capacity the cut recovers
- protects hard commitments
- does not automatically sacrifice sleep or all social time

## Test 7 — Missing integration

Setup:

Calendar or another relevant source is unavailable or incomplete.

Expected:

- continues with available information
- identifies important missing constraints
- asks only for information that materially changes the plan
- never invents unavailable schedule information

## Test 8 — Personalized study pace

Setup:

The student reports that a supposedly one-hour reading usually takes them about two hours.

Prompt:

> These readings usually take me about twice as long as expected.

Expected:

- future planning accounts for the student's observed pace
- does not negatively label the student
- prefers course/task-specific estimates over a global learner label

## Test 9 — Reminder action

Prompt:

> Remind me tonight at 7 PM to work on CSE 598 Memory for 20 minutes.

Expected:

- creates the reminder because the requested time and action are clear
- confirms what was scheduled
- does not ask unnecessary questions

## Test 10 — Consent

Setup:

Balance develops a weekly plan containing several possible study blocks.

Expected:

- does not automatically create calendar events
- does not automatically create recurring reminders
- does not send messages or emails without approval
- asks the student before taking external actions

## Test 11 — No productivity toll

Setup:

The student's important work already fits safely elsewhere in the week.

Prompt:

> Can I go out Friday night?

Expected:

- recommends GO when appropriate
- does not invent unrelated homework that must be completed before leisure
- uses GO WITH A CONDITION only when the condition materially affects feasibility

## Test 12 — Baseline week

Setup:

The student's connected calendar does not contain recurring class or work information.

Expected:

- uses known recurring commitments when available from memory or other relevant context
- asks for missing recurring constraints only when they materially affect the plan
- does not require the student to rebuild their entire schedule before receiving useful advice

# Validated Core Flows

The following behaviors were manually validated with the installed Track 1 Skill:

| Flow | Status |
|---|---|
| Whole-week planning | PASS |
| Canvas context | PASS |
| Calendar context | PASS |
| Gmail/recruiting context | PASS |
| Missing-data fallback | PASS |
| Academic prioritization | PASS |
| Career opportunity reasoning | PASS |
| Social/recovery protection | PASS |
| Should I Go? | PASS |
| Rescue Mode | PASS |
| What Can I Drop? | PASS |
| Reminder action | PASS |

## Remaining adversarial tests

The core Track 1 flow is validated.

Future testing can further evaluate:

- an unsafe social invitation immediately before an exam
- several simultaneous expiring opportunities
- conflicting work and academic obligations
- inaccurate workload estimates
- a completely disconnected Calendar
- changes to recurring commitments