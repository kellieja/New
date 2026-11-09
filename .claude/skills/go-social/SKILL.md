---
name: go-social
description: Social media and video menu. Picks the right skill for account setup, post planning, video, AI avatars, communities, or influencers.
disable-model-invocation: true
argument-hint: "[what you need for social]"
---

# Social and video

Pick one skill from the table, load it with the Skill tool, and do the work. Say in one line which skill you used. If the request spans two rows, run them in order.

| If they want to... | Use |
|---|---|
| Set up or fix social accounts, choose channels, profile checklist | `social-media-setup` |
| Plan posts, write posts, content calendar, grow followers | `social` |
| Make a video (scripts, editing, AI video tools) | `video` |
| Write a Seedance video prompt | `anthropic-skills:seed-dance` |
| A video with an AI presenter or spokesperson | `seedance-ai-avatar` |
| Graphics for posts | `image` |
| Build a community (groups, Discord, Slack) | `community-marketing` |
| Work with influencers or creators | `influencer-marketing` |

New client with no social presence yet: start with `social-media-setup`, then `social`.
AI avatars: disclose that the person is AI-generated, and get legal sign-off for political clients.
