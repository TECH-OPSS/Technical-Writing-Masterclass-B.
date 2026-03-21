# Deterministic Writing

**Same Instructions → Same Results → No Confusion**

---

## What It Means

Deterministic writing means writing instructions so that every person who follows them will get exactly the same result. There is no guessing. No hidden meanings. No missing details.

* One instruction must mean one thing only.
* One meaning must produce one action.
* Any difference in results means the writing is wrong.

Think of it like a machine: same input, same output, every time. Words are tools to show exactly what to do, not to explain or justify.

---

## Quick Test

Instruction:

```id="tst1"
"Process the request"
```

Problems:

* What is “request”?
* How should it be processed?
* What result is expected?

Because these are not clear, different readers will do different things. This is not deterministic.

---

## How It Works

Treat writing like a function:

```id="f1a8kc"
Output = Function(Instruction, Input, Environment)
```

It must work the same for everyone:

```id="d4p2mz"
All readers → Output same
```

To achieve this:

* Input must be fully defined
* Steps must be fully explained
* Environment (like software versions) must be clear

If something is left out, readers will interpret it differently, creating mistakes.

---

## Sources of Confusion

1. **Ambiguity** – Words or phrases can mean more than one thing.
2. **Missing Rules** – Some steps or limits are not explained.
3. **Hidden Knowledge** – You assume the reader knows something you didn’t write.
4. **Undefined Input** – Data is not fully described.

---

## Check Yourself

Instruction:

```id="tst2"
"Scale the system when needed"
```

* What does “needed” mean?
* How should it be scaled?
* What is the limit?

Without these, readers will act differently. Not deterministic.

---

## Writing Instructions

Rules for each step:

* **One task at a time** – no combined operations
* **Fully explained** – everything the reader needs is written
* **Clear start and end** – when to start and finish

Wrong:

```id="bad1"
Optimize performance
```

Right:

```id="good1"
If response time > 200ms → Add one server replica
```

Now the reader knows exactly what to do.

---

## Test Example

Instruction:

```id="tst3"
"Clean the dataset"
```

Check:

* What does “clean” mean? Remove empty values? Deduplicate?
* What is the format?
* How to handle errors?

If two people do different things, the writing is not deterministic.

---

## Using Words Clearly

Words must always mean one thing. No swapping synonyms. No hidden meanings.

Example:

```id="def1"
Authenticated = token is valid AND token is not expired
```

This definition must stay the same throughout the document.

---

## Test Example

Terms:

* “user”
* “client”
* “account”

If you use them interchangeably, pick one and stick to it.

---

## Rules and Conditions

All “if” statements must be measurable and testable. Avoid vague terms like “high” or “fast.”

Wrong:

```id="bad2"
If system load is high
```

Right:

```id="good2"
If CPU usage > 80% for 5 minutes
```

---

## Test Example

Instruction:

```id="tst4"
"If traffic is heavy"
```

Define exactly:

* Metric (requests/sec)
* Threshold value
* Time window

Otherwise, readers will guess.

---

## Dependencies

Every step must list everything it depends on. Missing dependencies create mistakes.

Wrong:

```id="bad3"
Run migration
```

Right:

```id="good3"
Run migration on database users, version 3.2, with backup enabled
```

---

## Test Example

Instruction:

```id="tst5"
"Deploy application"
```

Check if the instruction includes:

* Environment
* Version
* Configuration
* Rollback plan

If any are missing → non-deterministic.

---

## Order Matters

Steps must be in clear order when it matters.

Wrong:

```id="bad4"
Validate and store data
```

Right:

```id="good4"
Validate(data) → Store(data)
```

---

## Test Example

Instruction:

```id="tst6"
"Encrypt and send data"
```

Clarify order:

* Encrypt first
* Then send

Otherwise, readers may do it differently.

---

## States and Transitions

All system states must be explicit. Don’t assume hidden states.

Example:

```id="state1"
Pending → (payment success) → Confirmed  
Pending → (payment fail) → Failed
```

---

## Test Example

Instruction:

```id="tst7"
"Order is processed"
```

Check if all states are clear:

* Initial state
* Trigger
* Outcome
* Failure state

If not → non-deterministic.

---

## Errors

Define exactly what happens when things go wrong.

Wrong:

```id="bad5"
Handle errors appropriately
```

Right:

```id="good5"
If timeout → Retry 3 times with 2-second delay  
If still failing → Log error and abort
```

---

## Test Example

Instruction:

```id="tst8"
"If request fails, retry"
```

Define:

* What counts as failure
* Number of retries
* Delay
* Fallback if still failing

---

## Inputs and Outputs

Always define what the instruction takes in and what it produces.

Example:

```id="io1"
Input: {amount: float, currency: string, user_id: int}  
Output: {status: success or fail, code: int}
```

---

## Test Example

Instruction:

```id="tst9"
Process transaction(amount)
```

Check:

* Currency?
* User ID?
* Payment method?

All must be defined.

---

## No Hidden Defaults

Do not rely on assumed default values. Define everything.

Wrong:

```id="bad6"
Use default timeout
```

Right:

```id="good6"
Timeout = 30 seconds
```

---

## Test Example

Statement:

```id="tst10"
"Use default configuration"
```

Ensure default is defined. Otherwise, different readers may apply different defaults.

---

## Parallel Steps

If steps run at the same time, define order and synchronization. Otherwise, results may differ.

Wrong:

```id="bad7"
Run tasks simultaneously
```

Right:

```id="good7"
Run Task A and Task B in parallel  
Wait until both finish → Continue
```

---

## Test Example

Instruction:

```id="tst11"
"Execute jobs at the same time"
```

Define:

* How to synchronize
* How to handle failure

---

## Validation

Check deterministic writing with:

1. **Reader Convergence Test** – multiple readers produce the same result
2. **Path Uniqueness Test** – one input → one path
3. **Completeness Test** – all inputs covered
4. **Boundary Test** – start and end states defined

---

## Test Yourself

Take any vague instruction. Rewrite it clearly.
Then check:

* Can two people do it differently? If yes → not deterministic
* Are all inputs and conditions defined?
* Are outputs measurable?

---

## Failures to Avoid

* **Under-specification** – missing constraints → multiple outcomes
* **Over-generalization** – vague terms → guessing required
* **Hidden dependencies** – missing prerequisites → inconsistent execution

---

## Real-World Examples

### API

Wrong:

```id="api1"
Send required fields
```

Right:

```id="api2"
POST /payment  
Body: {amount: float > 0, currency: ISO_4217, user_id: int}  
If amount <= 0 → Reject(code=400)
```

---

### Deployment

Wrong:

```id="dep1"
Deploy latest version
```

Right:

```id="dep2"
Deploy image=service:v1.4.2 to production environment using config=hash_xyz
```

---

## Final Check

Deterministic writing is complete when:

* Only one meaning exists for each instruction
* Every input produces one predictable result
* Readers cannot guess or assume anything

At this point:

* Text = Clear instruction
* Reading = Execution
* Result = Identical every time
