## 📘 Module 10: Collaborating with Subject Matter Experts (SMEs)

---

> "Technical writing becomes exceptional when paired with technical truth." — Unknown

---

### 🎯 Module Objective

To train technical writers in building effective collaboration workflows with Subject Matter Experts (SMEs), mastering technical interview strategies, and ensuring content accuracy for high-stakes documentation.

---

### 🧠 Learning Outcomes

By the end of this module, you will:

* Understand the role of SMEs in documentation workflows
* Conduct focused, respectful, and productive interviews with SMEs
* Develop technical content through iterative validation
* Apply review cycles that preserve content integrity
* Navigate challenging collaboration scenarios with confidence

---

### 🧩 Core Concepts

#### 1. **Who Are Subject Matter Experts (SMEs)?**

SMEs are professionals with deep knowledge in a specific domain—developers, system architects, product managers, cybersecurity analysts, etc.—whose input is essential for:

* Ensuring technical accuracy
* Explaining backend workflows
* Clarifying edge cases or exceptions
* Validating that documentation aligns with system behavior

**Types of SMEs:**

* **Product SMEs** (Product Managers, UX Researchers)
* **Technical SMEs** (Developers, Architects)
* **Operational SMEs** (Support Analysts, SREs)
* **Regulatory SMEs** (Compliance, Legal, QA)

#### 2. **Why Writers Must Work Closely with SMEs**

* **Reduce Errors**: Prevent misunderstandings from reaching end-users
* **Accelerate Learning Curve**: Writers gain context more rapidly
* **Build Trust**: Involving SMEs builds collaborative credibility
* **Documentation Integrity**: SME-reviewed content stands up to scrutiny

---

### 🧰 SME Collaboration Frameworks

#### 3. **The Writer-SME Collaboration Lifecycle**

1. **Pre-interview Research**: Writer reads project briefs, requirements, or source code
2. **Initial Meeting**: Establish expectations and documentation goals
3. **Interview Sessions**: Gather information, ask clarifying questions
4. **Drafting**: Writer structures and formats initial content
5. **SME Review**: SME provides feedback, corrections, and clarifications
6. **Revision and Finalization**: Updated drafts go through final reviews
7. **Sign-off or Approval**: SME signs off to ensure content accuracy

#### 4. **SME Persona Profiles**

**Persona 1: Backend Developer - Rajiv**

* Expert in API development and microservices
* Time-constrained, prefers technical brevity
* Expects writers to understand JSON structures and endpoint documentation

**Persona 2: Product Manager - Lisa**

* Focuses on user journey and product value
* Prefers flowcharts, feature impact summaries
* Engages best via structured interviews with bullet points

**Persona 3: QA Analyst - Yusuf**

* Obsessed with accuracy and corner cases
* Wants detailed instructions for test procedures
* Documents everything in spreadsheets

**Persona 4: Site Reliability Engineer (SRE) - Anita**

* Ensures uptime and monitors system performance
* Expects documentation to explain fallback mechanisms and logs
* Will flag vague or risky recommendations immediately

---

### 🎙️ Conducting Effective Technical Interviews

#### 5. **Preparation Is Everything**

Before interviewing an SME:

* Study source documentation, previous versions, and Jira tickets
* Identify contradictions and assumptions to clarify
* Prepare a list of open and closed questions
* Respect SME’s preferred communication mode (call, async doc, or Slack)

#### 6. **Extended Interview Transcript (Annotated)**

**Topic:** API Authentication

**Writer:** "Can you walk me through the authentication logic once the user clicks ‘Login’?"

**SME:** "Sure, the login endpoint verifies the username and password using bcrypt, then generates a JWT which includes user ID and roles."

**Annotation:**

* *Highlight:* `JWT includes user ID and roles`
* *Clarify:* Ask if token expiration time is fixed or dynamic
* *Confirm:* Is there a refresh token process?

**Writer:** "How long does the JWT stay valid and how does it expire?"

**SME:** "By default, it’s 15 minutes, and the refresh token is valid for 7 days."

**Writer:** "What happens when the refresh token is expired?"

**SME:** "User has to re-authenticate. But we do send them a reminder prompt before that."

**Annotation:**

* *Note UX implication*: Add to onboarding guide
* *Insert flowchart*: Authentication + expiration states

---

### 🕵️‍♀️ Validating Documentation for Technical Accuracy

#### 7. **Cross-Referencing Methods**

* **GitHub PR Review**: Compare implementation vs written description
* **Swagger/OpenAPI Spec**: Match parameters and responses
* **Staging Demo**: Run through the product and ensure flow matches documentation
* **Exception Logs**: Verify how errors are logged, surfaced, or hidden from UI

#### 8. **Terminology Alignment Table**

| Term A         | Term B      | Canonical Term | SME Owner |
| -------------- | ----------- | -------------- | --------- |
| Access ID      | User Token  | Access Token   | Rajiv     |
| Log File       | Audit Trail | Audit Log      | Anita     |
| Session Cookie | Auth Cookie | Auth Cookie    | Yusuf     |

---

### 🛠 Technical Validation Case Studies

#### Case Study 1: Mismatched API Fields

**Background:** The documentation for the `POST /checkout` endpoint listed a `shippingID`, but backend returns `shipment_id`.

**Detection:** Writer spotted inconsistency after comparing OpenAPI and staging response

**Resolution:** Confirmed with Rajiv; updated docs to reflect `shipment_id`

**Lesson:** Don’t assume field names—even small differences can break integrations

#### Case Study 2: Incorrect Limitations Stated

**Issue:** Writer stated that the system only accepts .jpg uploads

**SME Review:** Anita clarified it also accepts .png and .webp

**Fix:** Document revised; added max file size, supported extensions, and compression logic

**Takeaway:** Always ask SMEs to validate limitations and constraints

---

### 🧾 SME Communication Templates

#### SME Availability Tracker

| SME   | Role        | Preferred Contact | Last Interview | Follow-up Needed |
| ----- | ----------- | ----------------- | -------------- | ---------------- |
| Rajiv | Backend Dev | Slack             | July 10        | Yes              |
| Lisa  | Product Mgr | Email             | July 15        | No               |
| Yusuf | QA Analyst  | Call              | July 12        | Yes              |
| Anita | SRE         | Google Meet       | July 11        | Yes              |

#### SME Review Checklist

* [ ] Terminologies align with system naming conventions
* [ ] Code snippets execute correctly
* [ ] Error conditions match real behavior
* [ ] Sequence of operations matches execution logic
* [ ] Known limitations are clearly stated

---

### 🤝 Best Practices for SME Relationships

* Acknowledge their time and contributions publicly
* Share preview links before publishing content
* Use version control to track changes across drafts
* Avoid overloading with too many simultaneous requests
* Educate SMEs on documentation impact during onboarding

---

### 🚧 Conflict Management Techniques

#### Problem: Two SMEs give conflicting system descriptions

**Approach:**

* Create a shared Google Doc
* Log both views under different sections
* Schedule a joint call
* Let each SME explain logic to the other
* Update documentation with verified flow

#### Problem: SME won’t respond

**Approach:**

* Resend email with bullet list of needed inputs
* CC their team lead
* Proceed with drafting but add a disclaimer
* Mark areas requiring confirmation with TODOs

---

### 🧪 Technical Review Simulations

1. **Exercise**: Review an API guide with two errors embedded; highlight them and draft a query email
2. **Exercise**: Turn a Zoom interview transcript into a formal 2-page user guide draft
3. **Exercise**: Given a vague response (“It just works”), write 3 follow-up questions to clarify behavior

---

### 🧗 Advanced Techniques

* Use diagrams to visualize technical flows before writing
* Version your interview notes using Markdown or Notion templates
* Tag SMEs in document comments for direct contextual feedback
* Pre-fill review checklists to make SME feedback faster

---

### ✅ Summary

SMEs are indispensable allies. Working with them ensures your documentation isn't just good—it’s accurate, authoritative, and usable. Your role as a technical writer is to extract and distill their deep technical knowledge into clear, accessible guidance for developers, end-users, and stakeholders.

---

### 📈 Mastery Outcomes

You now have:

* A tested approach to interviewing SMEs
* Familiarity with different SME personas
* Techniques for reconciling conflicts and validating workflows
* Templates to streamline communication and reviews
* Real-world insight into documentation verification strategies

---
