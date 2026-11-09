---
name: go-ads
description: Ads and tracking menu. Picks the right skill for paid campaigns, ad copy and creative, tracking setup, attribution, or A/B tests.
disable-model-invocation: true
argument-hint: "[what you need for ads or tracking]"
---

# Ads and tracking

Pick one skill from the table, load it with the Skill tool, and do the work. Say in one line which skill you used. If the request spans two rows, run them in order.

| If they want to... | Use |
|---|---|
| Plan, run, or fix a paid campaign (Google, Meta, LinkedIn) | `ads` |
| Write or test ad headlines, text, or creative | `ad-creative` |
| Set up GA4, events, UTMs, or check tracking works | `analytics` |
| Get conversions into ad platforms (pixels, CAPI) | `conversion-tracking` |
| Figure out which channel actually drives sales | `attribution` |
| Test two versions to see which wins | `ab-testing` |

Ads with no tracking: set up `analytics` and `conversion-tracking` before spending.
Financial, healthcare, and political ads have platform-specific rules; check them before launch.
