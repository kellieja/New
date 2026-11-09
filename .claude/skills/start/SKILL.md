---
name: start
description: Front door for every skill. Say what you need in plain words and the right skill runs. Use when you don't know which skill to pick.
disable-model-invocation: true
argument-hint: "[what you need, in plain words]"
---

# Start

The user does not want to pick skills. Read what they asked for, choose the right skill, load it with the Skill tool, and do the work. Never make them choose from a long list.

## How to route

1. Match the request to one area in the table below.
2. Within that area, pick the single best skill from the area's menu (open the `go-*` skill for that area and follow its table).
3. If the request spans two areas, run them in order and say so in one line, e.g. "Writing the page copy first, then the SEO pass."
4. If the request is genuinely unclear, ask one short question with two to four options. Otherwise start and state your assumption.
5. Tell the user in one line which skill you used, so they learn the shortcut for next time.

## Areas

| If they want to... | Area | Shortcut |
|---|---|---|
| Write or fix words: web pages, emails, headlines, ads copy, texts | Writing | `/go-write` |
| Design or build a website, page, or graphic, or review a design | Design and websites | `/go-design` |
| Social media: set up accounts, plan posts, make video | Social and video | `/go-social` |
| Get found on Google or in AI answers | SEO | `/go-seo` |
| Run or fix paid ads, or set up tracking | Ads and tracking | `/go-ads` |
| Turn more visitors into leads or customers | Conversion | `/go-convert` |
| Plan marketing, launch, price, or position an offer | Strategy | `/go-grow` |
| Find prospects, write outreach, support sales | Sales | `/go-sales` |
| 3D on a website | 3D | `/go-3d` |
| Brand voice, visual identity, or style guide | Brand | `/brand` |

## Rules that apply everywhere

- Never invent statistics, testimonials, results, or credentials. Numbers in examples are placeholders.
- Healthcare, financial, and political clients need claims they can back up. Flag anything that needs legal or compliance review.
- Draft outreach and posts for approval. Never send or publish on the user's behalf without explicit approval of the copy and the list.
