# Writing for Developers (API, SDK & Code Docs)

## 🎯 Objectives

* Learn how to write clear, developer-friendly documentation that supports smooth integration and developer onboarding.
* Understand the core elements of APIs, SDKs, and code documentation.
* Equip product managers (PMs), software engineers, and technical writers with tools and frameworks to effectively communicate technical details.
* Offer practical experiences, brain teasers, and interactive activities to deepen learning.
* Provide a platform for members to share real-world examples and insights.

---

## 🔍 Topics Covered

### 1. API Fundamentals: Endpoints, Parameters, Responses

APIs (Application Programming Interfaces) are contracts between systems. They define how different software components should interact.

**Key Concepts:**

* **Endpoints**: URL paths that represent an object or resource.
* **HTTP Methods**: `GET`, `POST`, `PUT`, `DELETE`.
* **Parameters**:

  * *Path Parameters*: Part of the URL (e.g., `/users/{id}`).
  * *Query Parameters*: Appended to the URL (e.g., `?limit=10`).
  * *Body Parameters*: Data passed in the request body (usually for `POST`/`PUT`).
* **Responses**: Standard format (usually JSON), status codes (e.g., `200 OK`, `404 Not Found`, `500 Internal Server Error`).

**Example:**

```http
GET /api/v1/products/123
Response:
{
  "id": 123,
  "name": "TechOps Gadget",
  "price": 199.99
}
```

**Engineer Tip**: Always use meaningful response codes and descriptive error messages.

**PM Insight**: Understand the high-level logic of how your product integrates with other platforms.

**Writer Guidance**: Use consistent terminology and add cross-references to related API methods.

**Brain Teaser**: Why is `PUT` idempotent while `POST` is not?

---

### 2. Explaining SDKs and Libraries

SDKs (Software Development Kits) and libraries make it easier to interact with APIs. They abstract complexity and offer high-level access points.

**Key Concepts:**

* SDKs may include:

  * API wrappers
  * Authentication helpers
  * Error handlers
  * CLI tools
* SDK documentation includes:

  * Installation steps
  * Authentication setup
  * Sample usage
  * Method definitions

**Example:**

```python
from techops_sdk import Client

client = Client(api_key="YOUR_KEY")
product = client.get_product(123)
print(product.name)
```

**Engineer Tip**: Document both the underlying API and SDK usage patterns.

**PM Insight**: Ensure SDKs are versioned correctly and backward-compatible.

**Writer Guidance**: Show how to get started fast. Include CLI examples and GitHub repo links.

**Brain Teaser**: How would you design an SDK wrapper to support both sync and async workflows?

---

### 3. Code Snippet Formatting

Great documentation includes well-formatted code samples. This helps developers copy-paste with confidence.

**Formatting Tips:**

* Use syntax highlighting.
* Show full context: imports, initialization, edge cases.
* Avoid hardcoded secrets.
* Be language-inclusive (show Python, JavaScript, etc.).

**Example:**

```javascript
// JavaScript Example using Fetch API
fetch('https://api.techops.io/products/123', {
  headers: {
    'Authorization': 'Bearer YOUR_KEY'
  }
})
.then(response => response.json())
.then(data => console.log(data));
```

**Engineer Tip**: Auto-generate code samples from OpenAPI specs.

**Writer Guidance**: Maintain a single source of truth using reusable code blocks.

**PM Insight**: Use documentation to reduce developer churn and support queries.

**Practical Activity**: Format code snippets for the same endpoint in Python, Ruby, and Go.

---

### 4. OpenAPI & Swagger Basics

OpenAPI is a standard for describing REST APIs. Swagger is a set of tools for generating docs, code, and testing interfaces from OpenAPI specs.

**Key Concepts:**

* **OpenAPI YAML/JSON format**
* **Swagger UI for visualization**
* **Endpoints auto-documentation**
* **Integration Testing via Swagger**

**Sample OpenAPI snippet:**

```yaml
paths:
  /products/{id}:
    get:
      summary: Get a product
      parameters:
        - in: path
          name: id
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Successful response
```

**Writer Guidance**: Start with Swagger editor to visualize the structure.

**Engineer Tip**: Use annotations in code to auto-generate OpenAPI specs.

**PM Insight**: Swagger docs can act as the single source of truth for the development and QA teams.

**Brain Teaser**: What are the limitations of OpenAPI in describing asynchronous APIs (e.g., WebSockets)?

---

### 5. Tutorials, Quickstarts, and Sample Use Cases

Beyond references, developers need walkthroughs and sample projects to truly understand an API.

**Tutorial Types:**

* **Quickstarts**: 5-minute setup to test API.
* **End-to-End Guides**: Build real apps using APIs.
* **Integration Samples**: How to plug APIs into popular frameworks (e.g., React, Django).

**Example Quickstart Flow:**

1. Register for API Key.
2. Make a test call.
3. Create a new object.
4. Handle the response.

**Writer Tip**: Include a screenshot or curl command for each step.

**Engineer Tip**: Maintain sample codebases alongside the API version.

**PM Insight**: Track user friction through analytics or developer feedback.

**Activity**: Write a 5-step tutorial on integrating your API with Node.js and React.

---

## 🔧 Role Relevance

### Engineers:

* Write self-documenting code that works with OpenAPI tools.
* Help QA and support teams understand API structure.
* Contribute to SDK development.

### Technical Writers:

* Improve readability and discoverability of API documentation.
* Ensure consistency across endpoints and versions.
* Collaborate with engineers to generate code samples.

### Product Managers:

* Understand integration workflows and challenges.
* Communicate API capabilities with clients and internal teams.
* Help prioritize documentation backlog.

**Practical Tip**: Each role should participate in at least one docs sprint per quarter to align on changes.

---

## ✅ Deliverables

### 1. Draft API Reference for a Mock Product

You will receive a set of endpoints and be asked to:

* Write a concise description for each
* Define parameters, responses, and examples
* Add code samples in 2+ languages
* Use OpenAPI 3.0 format

### 2. Quiz: Interpret Swagger Docs

Sample quiz questions:

* What does a `401` response mean in a Swagger doc?
* How are `query` and `path` parameters declared?
* Write a curl command based on Swagger doc snippet.

---

## 📊 Sharing Real-World Insights

We encourage you to contribute:

* Docs you’ve written for APIs/SDKs
* Examples of developer onboarding experiences
* Challenges you’ve faced documenting async APIs or complex auth flows
* Lessons from working with external clients

**Forum Thread**: "What’s the most confusing API you’ve ever used — and how would you improve the docs?"

**Live Panel**: Weekly API Jam where members show off their documentation projects.

---

## 🧠 Brain Teasers & Activities Summary

1. **Idempotency Puzzle**: Why is `PUT` idempotent?
2. **Async Design**: Design a Swagger doc for a WebSocket API.
3. **SDK Wrapper Challenge**: Support both sync/async operations.
4. **Code Formatter**: Format a single API call in 3 languages.
5. **Quickstart Creator**: Draft a 5-step tutorial for your API.
6. **Swagger Detective**: Interpret a complex OpenAPI snippet.

---

## 🔍 Further Reading & Tools

* [Swagger Editor](https://editor.swagger.io/)
* [OpenAPI Spec](https://swagger.io/specification/)
* [Postman](https://www.postman.com/)
* [Redoc](https://redocly.com/)
* [Stoplight](https://stoplight.io/)
* [ReadMe](https://readme.com/)
* [API Evangelist Blog](https://apievangelist.com/)
* [Stripe Docs (Best Practice)](https://stripe.com/docs)

Let’s make developer documentation clear, delightful, and powerful.

✨ Happy Writing! ✨
