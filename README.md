# Login Automation – Email Login (Katalon Studio)

This project demonstrates how I design and implement a maintainable QA automation solution for a critical user flow: **Login using Email and OTP**.
The focus is not on covering everything, but on **showing good testing decisions, structure, and trade-offs** that are suitable for a real production team.

---

## Why This Scenario?
Login is a **high-risk, high-traffic** area.  
A small validation bug can lead to:
- OTP abuse
- Increased infra cost
- Poor user experience

This automation validates the **happy path** and critical UI logic **before OTP verification**, where most regressions usually happen.

---

## What This Automation Covers
- Navigate to **Email Login**
- Input a **valid email** (data-driven)
- Toggle **Terms & Privacy Policy**
- Assert **Masuk button enabled state**
- Trigger **OTP send**
- Verify **navigation to OTP screen**
  
> OTP verification is intentionally skipped to keep tests **fast, stable, and CI-friendly**.

---

## What This Project Is Demonstrating
✔ Page Object Model for maintainability  
✔ Explicit waits (no hard delays)  
✔ Data-driven testing (easy to extend)  
✔ CI-ready execution  
✔ Clear separation of test logic, data, and environment  

---

## Tech Stack
- **Automation Tool:** Katalon Studio
- **Language:** Groovy
- **Platform:** Web (Chrome)
- **Pattern:** Page Object Model
- **Test Level:** Smoke / Functional
- **Reports:** HTML & JUnit (CI compatible)

---

## How to Run Locally
1. Open project in **Katalon Studio**
2. Run test suite: **Login**
3. Browser: **Chrome**

---

## How to Run in CI
```bash
katalonc -noSplash -runMode=console \
  -projectPath="katalon-login-automation.prj" \
  -testSuitePath="Test Suites/Login" \
  -executionProfile="qa" \
  -browserType="Chrome"
```

## How This Can Be Extended
- Negative & edge case validation
- Mobile automation (Appium)
- Parallel execution
- Accessibility checks


Thanks for reviewing this assessment.

<img width="1906" height="973" alt="image" src="https://github.com/user-attachments/assets/ab174fd1-2369-4e13-9cf4-f6abe1c3d0d6" />

