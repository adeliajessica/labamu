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
- (Optional) Observe OTP API request for correctness

> OTP verification is intentionally skipped to keep tests **fast, stable, and CI-friendly**.

---

## What This Project Is Demonstrating
✔ Page Object Model for maintainability  
✔ Explicit waits (no hard delays)  
✔ Data-driven testing (easy to extend)  
✔ CI-ready execution  
✔ Clear separation of test logic, data, and environment  

This is how I would structure automation in a **real team environment**.

---

## Tech Stack
- **Automation Tool:** Katalon Studio
- **Language:** Groovy
- **Platform:** Web (Chrome)
- **Pattern:** Page Object Model
- **Test Level:** Smoke / Functional
- **Reports:** HTML & JUnit (CI compatible)

---

## Project Structure (Simplified)
Profiles/ → environment configuration
Test Data/ → CSV test fixtures
Object Repository/ → page objects
Keywords/ → reusable utilities (API intercept)
Test Cases/ → test scenarios
Test Suites/ → execution grouping
Reports/ → auto-generated results

## How to Run Locally
1. Open project in **Katalon Studio**
2. Select execution profile: **qa**
3. Run test suite: **TS_Login_Smoke**
4. Browser: **Chrome**

---

## How to Run in CI
```bash
katalonc -noSplash -runMode=console \
  -projectPath="katalon-login-automation.prj" \
  -testSuitePath="Test Suites/TS_Login_Smoke" \
  -executionProfile="qa" \
  -browserType="Chrome"
```

## Designed to run in:
- Jenkins
- GitHub Actions
- GitLab CI

## Reporting
After execution, reports are generated automatically:
- HTML report (human readable)
- JUnit XML (CI integration)

## Reports include:
- Execution status
- Timing
- Failure details
- Screenshots on error

## Trade-offs & Limitations
OTP verification is excluded (belongs to backend / integration testing)

## API mocking is minimal (intercept/log only)
- Focused on quality over quantity of test cases
- These trade-offs are deliberate to keep the suite stable and fast.

## How This Can Be Extended
- Negative & edge case validation
- Mobile automation (Appium)
- Parallel execution
- Accessibility checks


Thanks for reviewing this assessment.
