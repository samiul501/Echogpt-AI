# EchoGPT QA Project

## 📌 Executive Summary
This project presents a QA evaluation of the **Sign-up Feature** for EchoGPT.  
Testing was conducted using both **manual and automated strategies**, with a total of **39 test cases** executed across functional, non-functional, usability, and security areas.

### ✅ Overview of Findings
- **Total Test Cases:** 39  
- **Execution Summary:** 18 Passed | 3 Failed | 18 Not Executed  
- **Pass Rate:** 46% | **Fail Rate:** 8% | **Not Executed:** 46%  
- **Coverage Areas:** Functional validation, field input policies, email & OAuth integration, password security, usability, cross-browser checks, accessibility, and performance.  
- **Automation Tools:** Selenium (functional & cross-browser), JMeter (performance).  

---

## 📊 Quality Assessment
- **Overall Rating:** Good – major user flows (OAuth, input validation, password policies) worked as expected.  
- **Strengths:** Password strength enforcement, OAuth authentication, usability features (error messages, password masking).  
- **Gaps:** OTP scenarios untested (due to missing OTP delivery).  
- **Failures:**  
  - **TC034:** Session timeout handling  
  - **TC038:** Harmful content refusal  
  - **TC039:** Factual correctness validation  

---

## ⚠️ Risk Assessment & Recommendations
- **High Risks:**  
  - Harmful content refusal (TC038)  
  - Factual correctness validation (TC039)  

- **Medium Risks:**  
  - Session timeout handling (TC034)  

- **Execution Gaps:**  
  - OTP-related cases pending  

**Recommendations:**  
1. Fix failed cases & complete OTP execution before release.  
2. Perform regression testing after fixes.  
3. Run stress/load tests to validate performance.  
4. Strengthen automation with CI/CD integration.  

---

## 🤖 Automation Strategy

### 🎯 Objectives & Principles
- Risk-driven coverage (auth, payment, compliance).  
- Prioritize repeatable & stable scenarios.  
- Shift-left API validation for OTP/email/payment.  
- Convert failures (TC034, TC038, TC039) into must-run checks.  

### 🔑 Automation Candidates
- **Functional (High Priority):** Sign-up/Login, OAuth, password policy, field validation.  
- **Security Controls:** Password masking, session timeout.  
- **Payment Flow:** Option visibility, error handling.  
- **Non-Functional:** Cross-browser/device checks, performance, accessibility.  
- **AI-Specific:** Harmful content refusal, factual correctness validation.  

### 🛠 Recommended Tools
- **UI E2E:** Selenium WebDriver (Java/PyTest)  
- **API:** Postman/Newman, RestAssured  
- **Mobile:** Appium  
- **Performance:** JMeter / Locust  
- **Accessibility:** axe-core, Wave  
- **CI/CD:** GitHub Actions, Jenkins, Allure reports  

---

## 🔄 Regression Strategy
- **Smoke (per commit):** OAuth login, dashboard reachability, payment options.  
- **Daily Regression:** Auth flows, session timeout, browser matrix, moderation checks.  
- **Pre-Release:** Cross-device expansion, performance, accessibility, negative payment flows.  

---

## 📑 Appendix: Test Case Coverage (Summary)

| TC ID       | Area                         | Priority | Automate | Tool              |
|-------------|------------------------------|----------|----------|-------------------|
| TC001–TC004 | Email/OAuth basic sign-up    | High     | ✓        | Selenium          |
| TC005–TC014 | Field & policy validation    | High     | ✓        | Selenium          |
| TC015–TC016 | Google sign-in, email verify | High     | ✓        | Selenium + API    |
| TC021       | Password masking             | High     | ✓        | Selenium          |
| TC022       | Response time                | Medium   | ✓        | JMeter/Locust     |
| TC023–TC027 | Cross-browser/device         | High     | ✓        | Selenium          |
| TC028       | Accessibility                | Medium   | ✓        | axe-core          |
| TC032–TC033 | Payment validation/handling  | High     | ✓        | Selenium + API    |
| TC034       | Session timeout (Failed)     | Medium   | ✓        | Selenium          |
| TC038       | Harmful content refusal (❌) | High     | ✓        | Selenium + Oracle |
| TC039       | Factual correctness (❌)     | High     | ✓        | Selenium + Oracle |

---

## 📌 Next Steps
1. Fix and re-test failed scenarios (TC034, TC038, TC039).  
2. Execute OTP-dependent cases once service is operational.  
3. Conduct exploratory testing under slow/unstable networks.  
4. Expand automation into CI/CD pipelines for scalability.  
5. Schedule periodic regression & compliance testing.  

---

**Project:** EchoGPT QA Project  
**Author:** Samiul Islam  
**Date:** 26 Aug 2025  

---
