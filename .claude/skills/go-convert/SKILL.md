---
name: go-convert
description: Conversion menu. Picks the right skill for turning visitors into leads and customers, from landing pages and sign-up to onboarding, popups, upgrades, and churn.
disable-model-invocation: true
argument-hint: "[what you need to convert better]"
---

# Conversion

Pick one skill from the table, load it with the Skill tool, and do the work. Say in one line which skill you used. If the request spans two rows, run them in order.

| If they want to... | Use |
|---|---|
| A page that isn't converting (landing, home, pricing) | `cro` |
| Sign-up or registration flow | `signup` |
| New-user onboarding and activation | `onboarding` |
| Popups, banners, exit-intent | `popups` |
| In-app upgrade or paywall screens | `paywalls` |
| Stop customers canceling | `churn-prevention` |
| Test two versions | `ab-testing` |

Not sure where the leak is: start with `cro` on the page that gets the most traffic.
