# PunterClash API Test Automation

This repository contains automated API tests for the PunterClash platform, covering **Smoke**, **Regression**, and **End-to-End (E2E)** test flows.  
The tests are built using Postman collections and executed via Postman CLI, with integration into CI/CD pipelines using GitHub Actions.

---

## 📌 Purpose

The goal of this project is to:

- Validate critical API functionality
- Ensure system stability after deployments
- Provide fast feedback through automated smoke tests
- Support comprehensive regression testing
- Enable scalable E2E test coverage

---

## 🧱 Project Structure


---

## 🧪 Test Suites Overview

### 🔥 Smoke Tests
- Purpose: Validate that the system is operational
- Scope:
  - Login (static user)
  - Authenticated request
  - Logout
- Characteristics:
  - Fast execution
  - Deterministic
  - Runs on every push / PR

---

### 🧪 Regression Tests
- Purpose: Ensure no existing functionality is broken
- Scope:
  - Functional API tests
  - Negative scenarios
  - Edge cases
  - Token handling
- Characteristics:
  - Broader coverage
  - Slower execution
  - Run on schedule or before release

---

### 🔁 End-to-End (E2E) Tests

#### Authenticated Flow
- Login
- Access protected endpoints
- Logout

#### Onboarding Flow (Partial)
- Register user
- Trigger OTP flow
- Validate unverified login behavior

> ⚠️ Full onboarding E2E is pending OTP test support from backend.

---

## ⚙️ Environment Configuration

The environment file contains variables required for execution.

### Required Variables
static_user_phone
static_user_password

> These credentials must belong to a **verified and stable test user**.

---

## 🚀 Running Tests Locally

### Using Postman CLI

```bash
postman collection run collections/smoke.postman_collection.json \
  --environment environments/staging.postman_environment.json
