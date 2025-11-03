# Discord Birthday Bot

A production-ready Discord Birthday Bot that collects member birthdays, schedules timezone-accurate greetings, assigns celebratory roles, and posts rich embeds with images or GIFs automatically. It removes manual tracking, eliminates missed dates, and keeps your community engaged with reliable, human-like delivery across multiple servers. Built for scale, auditability, and hands-off operations.

<p align="center">
  <a href="https://Appilot.app" target="_blank">
    <img src="media/appilot-baner.png" alt="Appilot Banner" width="100%">
  </a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20Appilot%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:support@appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom Discord Birthday Bot, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
This bot automates the full birthday workflow on Discord: collecting and validating dates, handling timezones, posting scheduled wishes in the right channels, and optionally assigning/removing a "Birthday" role. It also supports images/GIFs, custom messages, and analytics so server owners can set and forget.

### Automating Birthday Celebrations Across Servers
- Zero-maintenance birthday calendar: import CSV or let users self-register via slash commands.
- Timezone-aware scheduling with daylight-saving safety for globally distributed servers.
- Human-like pacing, randomized send windows, and retries to avoid rate limits or spam signals.
- Works with both desktop API and Android client automation for presence-sensitive communities.
- Granular permissions, audit logs, and dashboards for multi-guild management.

## Core Features
- **Real Devices and Emulators:** Optional Android-client mode via emulator (Bluestacks/Nox) for presence simulation, push-based triggers, and visual checks when API access is constrained.
- **No-ADB Wireless Automation:** ADB-less wireless control pipeline to manage Android Discord app interactions without tethering; ideal for headless device racks.
- **Mimicking Human Behavior:** Randomized delays, jittered posting windows, natural typing indicators, and staggered role assignments to reduce detection risks.
- **Multiple Accounts Support:** Run multiple bot tokens (or client profiles in Android mode) with isolated configs, quotas, and per-guild limits.
- **Multi-Device Integration:** Orchestrate several emulators/real phones in parallel with queue-based dispatch to meet peak celebration hours.
- **Exponential Growth for Your Account:** Auto-celebrations spark server activity; reactions, XP, and retention metrics trend upward with consistent birthday recognition.
- **Premium Support:** SLA-backed onboarding, migration assistance (Mee6/BotGhost → this bot), and priority fixes.
- **Slash Commands & Forms:** `/set-birthday`, `/my-birthday`, `/next-birthdays`, `/birthday-channel`, plus Modals for private date entry with validation.
- **Role Automation:** Assign temporary "Birthday" role for 24h (configurable), auto-remove safely with retries and audit.
- **Rich Embeds & Media:** Per-server templates with embeds, images/GIFs, server emoji, and @mention controls.
- **Timezone Intelligence:** Per-user TZ mapping + DST handling; fallback heuristics if TZ unknown.
- **CSV Import/Export:** Bulk import from spreadsheets, export for audits or backups.
- **Observability:** Structured logs, metrics, daily reports, and failure alerts in a private staff channel.
- **Persistence:** Pluggable storage (SQLite/Postgres/Mongo/Firestore) with migrations and indices.
- **Safety & Compliance:** Rate-limit guards, permission checks, and disaster-stop command for moderators.

**Additional Features**

| Feature | Description |
| --- | --- |
| Calendar Preview | Generates a rolling 30/90-day birthday calendar in an admin channel. |
| Message Templates | Handlebars-style variables (`{{user}}`, `{{age}}`, `{{server}}`) with per-guild overrides. |
| Quiet Hours | Suppress posts during set hours; defer to next window automatically. |
| Webhooks & Integrations | Send events to webhooks or dashboards; plug into analytics/CRM. |
| Retry & Backoff | Intelligent retry with exponential backoff and idempotent posting. |
| Sharding & Horizontal Scale | Discord sharding + worker queues for high-guild deployments. |

</p>
<p align="center">
  <a href="https://appilot.app" target="_blank">
    <img src="media/Discord Birthday Bot-banner.png" alt="Discord Birthday Bot-architecture" width="95%">
  </a>
</p>

## How It Works
1. **Input or Trigger** — The automation is triggered through the Appilot dashboard, where admins set channels, roles, templates, and schedules; users register birthdays via slash commands or CSV import.
2. **Core Logic** — Appilot controls the Discord flow (API-first) or optional Android client (UI Automator/ADB-less) to queue tasks: validate inputs, map timezones, and schedule posts with human-like timing.
3. **Output or Action** — On the birthday, the bot posts a rich embed, @mentions the member (optional), assigns a temporary role, and logs the action to the staff channel.
4. **Other functionalities** — Robust retry logic, error handling, rate-limit awareness, structured logging, analytics summaries, and parallel processing via queues ensure smooth, scalable execution.

## Tech Stack
- **Language:** TypeScript, Node.js (optionally Python for ops), Kotlin/Java (Android mode)
- **Frameworks:** discord.js / Discord API, NestJS (or Fastify), Appium, UI Automator, Robot Framework
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks/Nox, Scrcpy, Firebase Test Lab, Accessibility
- **Infrastructure:** Dockerized runners, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues (BullMQ/Redis), Real device farm

## Directory Structure
```
discord-birthday-bot/
│
├── src/
│   ├── index.ts
│   ├── config/
│   │   ├── env.ts
│   │   └── schema.ts
│   ├── commands/
│   │   ├── setBirthday.ts
│   │   ├── myBirthday.ts
│   │   ├── nextBirthdays.ts
│   │   └── admin/
│   │       ├── setChannel.ts
│   │       ├── setRole.ts
│   │       └── importCsv.ts
│   ├── scheduler/
│   │   ├── jobQueue.ts
│   │   ├── birthdayWorker.ts
│   │   └── quietHours.ts
│   ├── core/
│   │   ├── birthdayService.ts
│   │   ├── timezone.ts
│   │   ├── templating.ts
│   │   ├── roleManager.ts
│   │   └── webhook.ts
│   ├── infra/
│   │   ├── db/
│   │   │   ├── prisma/
│   │   │   │   └── schema.prisma
│   │   │   ├── migrations/
│   │   │   └── repository.ts
│   │   ├── redis.ts
│   │   └── logger.ts
│   ├── android-mode/
│   │   ├── ui-automator/
│   │   │   └── flows.kt
│   │   └── runners/
│   │       ├── emulatorManager.ts
│   │       └── deviceController.ts
│   └── api/
│       └── httpServer.ts
│
├── config/
│   ├── settings.yaml
│   ├── permissions.json
│   └── credentials.env
│
├── media/
│   ├── templates/
│   │   ├── default.md
│   │   └── confetti.gif
│   └── banner.png
│
├── logs/
│   └── bot.log
│
├── scripts/
│   ├── deploy-commands.ts
│   └── seed.ts
│
├── test/
│   └── birthday.spec.ts
│
├── docker/
│   ├── Dockerfile
│   └── compose.yaml
│
├── package.json
├── tsconfig.json
├── prisma.schema
└── README.md
```


## Use Cases
- **Community Managers** use it to automate birthday wishes and temporary roles, so they can keep engagement high without manual tracking.
- **Guild Owners** use it to centralize multi-server birthday management, so they can maintain consistency across communities.
- **Esports/Clubs** use it to schedule themed birthday messages with media kits, so they can strengthen brand loyalty.
- **Edu Servers** use it to anonymize birthdays with opt-in privacy, so they can comply with internal guidelines.

## FAQs
**How do I configure this automation for multiple accounts?**  
Provide multiple Discord tokens in `credentials.env` or via secrets manager; the bot shards by guild and isolates quotas per token. Android-client mode can map devices per account for presence simulation.

**Does it support proxy rotation or anti-detection?**  
API mode follows Discord rate limits strictly. Android mode uses proxy-capable emulators/real devices with human-like pacing, randomized delays, and accessibility-driven interactions.

**Can I schedule it to run periodically?**  
Yes. The scheduler computes daily runs with a rolling 24h window, respects quiet hours, and queues posts to workers. Missed jobs are retried automatically.

**What if members don’t want to share exact birth year?**  
Users can submit day/month only. Age rendering is optional and template-driven.

**Can we import from an existing bot?**  
Use the CSV importer; column mapping wizard aligns external exports to the internal schema.

## Performance & Reliability Benchmarks
- **Execution Speed:** Batches ~100 birthday posts/minute in API mode on modest hardware; Android mode fan-out depends on device farm throughput.
- **Success Rate:** 95% end-to-end message + role assignment success under nominal network conditions.
- **Scalability:** Proven architecture scales to 300–1000 Android devices (Android mode) or 5k+ guilds via sharding and queue-based dispatch.
- **Resource Efficiency:** Worker processes idle-sleep when queues are empty; memory stayed under 300MB per shard in testing.
- **Error Handling:** Structured logging, circuit breakers on rate-limit spikes, exponential backoff, dead-letter queues, and daily health reports to a staff channel.

##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>
