# Browser Testing Prompt — User Journey

Act as a QA engineer using browser automation to test the Tekstain Nexus ESG and Carbon Management Platform.

Review the available PRD, Frontend PRD, Architecture document, and project instructions before testing. Use the running application and its actual interface; do not assume a feature exists if it is not implemented.

## Objective
Test the highest-priority end-to-end user journeys in a real browser, focusing first on critical paths and security-sensitive behavior.

## Test these journeys where supported
1. Sign in and sign out.
2. Create or open an organization and complete its basic profile.
3. Enter ESG data for a reporting period, validate it, and submit it.
4. Upload supporting evidence and check that it is associated with the correct record.
5. Review and approve or return a submission, if review workflows exist.
6. Run a supported carbon calculation and verify that its inputs, units, result, and emission-factor details are displayed consistently.
7. Generate and review an ESG report, then test its available export.
8. Check access controls by attempting to access another organization's data with an account that should not have permission.

## Instructions
- Use only authorized test accounts and synthetic test data. Do not expose or alter real customer data.
- Run journeys one at a time or in small logical groups. Record the steps, expected result, actual result, and evidence for each test.
- Check normal behavior, validation messages, loading and empty states, failures, navigation, and browser-console/network errors where available.
- Verify that data persists after refresh or navigation where persistence is expected.
- For calculations and reports, compare displayed results against the application’s documented rules and test data; do not invent expected emission factors or values.
- Prioritize critical failures involving authentication, organization-level data isolation, data integrity, carbon calculations, and report accuracy.
- If a journey cannot be tested because the feature, test account, or environment is unavailable, mark it **Blocked** and explain why. Do not report it as passed.
- Do not modify code, change configuration, or implement fixes unless explicitly instructed. If a test fails, report reproducible steps and a concise recommended fix.

## Final Report
Summarize:
- Environment and browser tested.
- Journeys tested and their status: **Passed, Failed, Blocked, or Not Tested**.
- Failures ranked by severity, with reproduction steps and supporting evidence.
- Relevant console or network errors.
- Risks and recommended next actions.

Report only checks actually performed. Do not claim the application passed tests that were not run.
