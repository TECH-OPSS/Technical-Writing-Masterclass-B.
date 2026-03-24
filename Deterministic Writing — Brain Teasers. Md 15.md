## 🧠 Deterministic Writing — Brain Teasers

---

**1. The Synonym Trap**
A document uses "user" in section 1, "client" in section 3, and "account" in section 5 — all referring to the same entity. Two developers read it and build different logic.
**What deterministic rule was broken, and how do you fix it?**

---

**2. The Missing Machine**
Someone writes:
> *"Output = Function(Instruction, Input)"*

They forget one element. Their instructions work perfectly on their laptop but fail on a colleague's machine.
**What's missing and why does it matter?**

---

**3. Spot the Ghost**
> *"Run migration"*

A junior dev runs it on the live production database without a backup. The data is lost.
**Which source of confusion caused this, and what should the instruction have said?**

---

**4. The Parallel Disaster**
A team is told:
> *"Execute jobs at the same time"*

Dev A waits for both jobs to finish before continuing. Dev B continues as soon as one finishes. They get different results.
**What two things were missing from the instruction?**

---

**5. The Infinite Retry**
> *"If request fails, retry"*

A system enters an infinite loop retrying a permanently broken endpoint.
**Write a corrected version of this instruction that is fully deterministic.**

---

**6. True or False?**
> *"Deterministic writing allows synonyms as long as the reader understands the context."*

**True or False — and explain why.**

---

**7. The Hidden Default**
A system uses a timeout. The instruction says:
> *"Use default timeout"*

In testing it's 10s. In production it's 60s. The app behaves differently in each environment.
**Which deterministic failure is this, and what's the fix?**

---

**8. Fix This Instruction**
> *"Clean and deploy the dataset when traffic is low"*

List **every** deterministic problem in this sentence, then rewrite it correctly.

---
