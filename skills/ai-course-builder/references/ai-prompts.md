# Staged AI prompts for course building

Use one prompt per stage. Preserve the instructor's original input and pause for human confirmation before moving to the next stage.

## 1. Course brief calibration

```text
You are a course-design diagnostic assistant.
I will provide a course idea, learner problems, and existing materials.

Do not write a course outline yet. First output:
1. verified facts;
2. my inferences;
3. missing information;
4. the result I need to confirm;
5. results I should not promise.

Check who the actual learners are, what problem repeats, what they must complete,
why the instructor can teach it, and what is outside this course.
If information is insufficient, output only an intake checklist.
```

## 2. Instructor experience map

```text
The following contains my spoken notes, cases, previous lessons, and judgments.
Do not invent experience, cases, outcomes, or evidence, and do not polish this into
course copy yet.

Organize it into three tables:
1. major modules: the main learner problems;
2. sub-problems: concrete learner obstacles under each module;
3. evidence and actions: my cases, judgment criteria, demonstrations, learner
   exercises, and expected artifacts.

Label each item as: verified fact / instructor judgment / external source /
unverified hypothesis. Preserve the original judgment and list questions where
the source is incomplete.
```

## 3. Course outline

```text
Based on the confirmed course brief, instructor experience map, benchmark notes,
result boundary, and constraints, produce a course outline.

For each module, specify:
- learner problem;
- learning objective;
- instructor judgment;
- learner action;
- learner artifact;
- case or demonstration;
- practice and feedback;
- condition for entering the next module.

Do not add unsupported modules or treat lesson count as value. Output structure
only and wait for confirmation of sequence and scope.
```

## 4. Expand one module

```text
Expand only [module or lesson].

Keep this order:
situation -> instructor judgment -> method -> real case -> demonstration/practice
-> common errors -> check standard -> summary -> next action.

Use only the provided experience, cases, and sources. Mark unsupported areas as
[TO VERIFY]. Keep it teachable and conversational rather than encyclopedic.
End with a list of items that require human confirmation.
```

## 5. Course quality check

```text
Audit the following course text without rewriting it.

Check:
- Are the actual learners and repeated problem clear?
- Is the end result observable, submittable, and reviewable?
- Does every lesson have an action and artifact?
- Does a case precede practice and does practice receive feedback?
- Did the draft introduce unsupported cases, numbers, promises, testimonials,
  or tool effects?
- Are there sequence jumps, duplication, or scope beyond the available time?
- Are privacy, provenance, course boundary, and human review gates explicit?

Output: passed items, risk items, required changes, and questions for the
instructor.
```

## 6. Retrospective and assetization

```text
The following is the real delivery record: registration, attendance, completion,
learner artifacts, questions, feedback, and instructor retrospective.

Separate it into:
1. facts: what happened;
2. observations: what worked or got stuck;
3. assets: methods, SOPs, cases, FAQs, templates, or prompts worth preserving;
4. iteration: what to remove, add, reorder, or change in format.

Only list an automation or agent candidate when the same process has repeated and
the rule is stable. Do not turn a one-off judgment into an automatic rule.
```
