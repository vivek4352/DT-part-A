# DT Fellowship Assignment — Write-up  
## The Daily Reflection Tree

---

## 1. Overview

This project designs a deterministic reflection agent that guides an employee through an end-of-day reflection using a structured decision tree.

The goal is not to generate advice, but to surface awareness across three psychological axes:

1. Locus (Victim ↔ Victor) — Where did I have control?
2. Orientation (Entitlement ↔ Contribution) — What did I give vs expect?
3. Radius (Self-Centric ↔ Altrocentric) — Who did I consider beyond myself?

The system is fully deterministic:
- No LLM at runtime  
- Fixed options for every question  
- Predefined branching logic  
- Consistent output for the same inputs  

The intelligence is encoded in the tree structure itself, not in any model.

---

## 2. Design Philosophy

### 2.1 Reflection, Not Evaluation

The system is designed to feel like a guided reflection, not an assessment.

- Questions are open but bounded (fixed options, but psychologically meaningful)
- Reflections avoid judgment or correction
- The tone is closer to a thoughtful colleague than a manager or therapist

The intention is:
> Help the user notice patterns, not tell them what is right or wrong.

---

### 2.2 Low Friction Entry

The first question:

> “If today were a weather report…”

This was intentionally chosen because:
- It is emotionally intuitive
- Requires minimal cognitive effort
- Allows users to enter reflection mode naturally

Starting with analytical questions would create resistance, especially at the end of the day.

---

### 2.3 Progressive Depth

The tree follows a layered structure:

| Stage | Focus |
|------|------|
| Axis 1 | Personal control (internal vs external) |
| Axis 2 | Behavior toward others (giving vs expecting) |
| Axis 3 | Perspective (self vs others) |

Each axis builds on the previous one:

- Recognizing agency (Axis 1) enables intentional contribution (Axis 2)  
- Contribution naturally expands into awareness of others (Axis 3)

This creates a single evolving conversation, not three separate assessments.

---

## 3. Question Design

### 3.1 Principles Used

Each question was designed with the following constraints:

- Clear distinction between options  
- No overlap or ambiguity where possible  
- Psychological honesty — options reflect real human behavior  
- Balanced framing — no option is obviously “correct”  

---

### 3.2 Axis 1 — Locus (Victim vs Victor)

Goal: Surface whether the user sees events as controlled by them or happening to them.

Examples:
- “What made it happen?” vs “What was your instinct when things got hard?”
- Follow-up questions identify presence or absence of choice

Design decision:
- Introduced a “mixed” path (e.g., pushing through) to capture ambiguity between control and reaction

---

### 3.3 Axis 2 — Orientation (Contribution vs Entitlement)

Goal: Shift focus from what I received to what I gave.

Design approach:
- Split users into:
  - Contribution-oriented paths
  - Expectation-oriented paths

Key insight:
- Entitlement is often invisible to the user, so questions reveal underlying needs (recognition, fairness, belonging)

Reflections validate the need without reinforcing passive thinking.

---

### 3.4 Axis 3 — Radius (Self vs Others)

Goal: Expand perspective beyond self.

Design approach:
- Start with: “Who comes to mind?”
- Then deepen:
  - If self-focused → ask about impact on others  
  - If other-focused → explore emotional meaning  

This axis aims to create a shift toward:
> “My experience” → “Our experience”

---

## 4. Branching Logic

### 4.1 Deterministic Routing

All branching is handled through:
- Explicit decision nodes
- Predefined mapping of answers → next node

Example:
Sunny|Mixed → Agency path   Cloudy|Stormy → Challenge path

This ensures:
- No randomness  
- Full traceability  
- Reproducibility  

---

### 4.2 Signal System

The tree tracks user tendencies using simple signals:

- axis1:internal / axis1:external
- axis2:contribution / axis2:entitlement
- axis3:selfcentric / axis3:altrocentric

These signals:
- Accumulate during the session  
- Determine dominant tendencies  
- Feed into the final summary  

---

### 4.3 Interpolation

Reflections use stored answers to personalize output:

Example:
> “You said '{A1_OPEN.answer}', but your actions show control.”

This creates the effect of:
- Personal relevance  
- Continuity across the conversation  
- Structured but meaningful feedback  

---

## 5. Trade-offs and Design Choices

### 5.1 Simplicity vs Depth

I chose:
- Fewer, clearer branches  
over  
- Highly complex tree structures  

Reason:
- End-of-day users are cognitively fatigued  
- Simplicity improves completion and engagement  

---

### 5.2 Fixed Options vs Expressiveness

Constraint:
- No free text allowed  

Trade-off:
- Some nuance is lost  
- But clarity and determinism are gained  

I mitigated this by:
- Designing options that capture common real-world patterns

---

### 5.3 Emotional Safety vs Directness

I avoided:
- Harsh or corrective language  

Instead:
- Reflections acknowledge reality
- Then gently redirect attention  

Example:
> “That need is real. Can you create that value yourself?”

---

## 6. What I Would Improve With More Time

1. Option-level signal granularity  
   - Assign signals per option instead of per node  

2. More adaptive reflections  
   - Combine multiple past answers for deeper personalization  

3. Richer Axis 3 exploration  
   - Add more layers to perspective-taking  

4. Expanded tree size  
   - More edge cases and nuanced paths  

5. Behavioral follow-up loop  
   - Suggest a small action for the next day  

---

## 7. Conclusion

This system demonstrates how human psychology can be encoded into a deterministic structure.

Instead of relying on generative AI, it:
- Guides thinking through designed pathways
- Creates insight through structured reflection
- Maintains consistency and trust through determinism

The core idea is:
> Insight does not require generation — it requires structure.

---