# 🏦 AI Financial QA Testing Suite

An automated **AI Quality Assurance (QA)** evaluation framework designed to test and validate strict business logic for financial authentication and payment systems using **Promptfoo** and **Google Gemini (`gemini-3.8-flash`)**.

---

## 🎯 Project Objective
Large Language Models (LLMs) used in financial applications must adhere to strict validation constraints without hallucinating or bypassing business rules. This project establishes an automated test suite verifying:
- **Phone Number Format:** Must start with `07`, be exactly 10 digits, and use English numerals.
- **Password Complexity:** Requires uppercase letters, special symbols, and no spaces.
- **Payment Precision:** Validates boundary limits (up to `999.99`), exact decimal precision (max 2 decimals), and rejects malformed values (e.g., standalone decimals like `.50` or amounts over `1000`).

---

## 🛠️ Tech Stack & Tools
- **Testing Framework:** [Promptfoo](https://www.promptfoo.dev/)
- **LLM Provider:** Google Gemini (`gemini-3.8-flash`)
- **Configuration:** YAML Test Suites & Automated Assertions
- **Version Control:** Git & GitHub

---

## 📋 Rule Validation & Assertion Matrix

| Rule Category | Input Field | Constraint / Condition | Expected Result |
| :--- | :--- | :--- | :--- |
| **Authentication** | Phone Number | Starts with `07`, 10 digits, English numerals | `Transaction approved` |
| **Authentication** | Phone Number | Invalid prefix (`08`), short length (9 digits), Arabic numerals | `Transaction rejected` |
| **Security** | Password | Contains uppercase letter and special symbol | `Transaction approved` |
| **Security** | Password | Missing uppercase or missing special character | `Transaction rejected` |
| **Payment** | Amount | Max 3-digit integer, max 2 decimals (`999.99` limit) | `Transaction approved` |
| **Payment** | Amount | Exceeding limit (`1000`), standalone decimal (`.50`), 3 decimals (`540.123`) | `Transaction rejected` |

---

## 🚀 How to Run the Tests

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/ayhamewidat-blip/AI-financial-QA-Test.git]
   cd AI-financial-QA-Test