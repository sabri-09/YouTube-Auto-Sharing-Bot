# YouTube Auto Sharing Bot

This project automates sharing YouTube videos to social channels like **Facebook**, **Twitter (X)**, and **Reddit** directly from Android devices and emulators. It removes copy-paste fatigue, enforces consistent captions/hashtags, and scales distribution across multiple accounts and devices with human-like pacing. The **YouTube Auto Sharing Bot** helps creators and teams boost reach, cut posting time, and keep brand messaging uniform.

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
   <strong>If you are looking for custom YouTube Content Performance Analyzer, you've just found your team — Let’s Chat.👆👆</strong>
</p>


## Introduction

**What it does:** Automates end-to-end sharing of YouTube videos (links or shorts) to Facebook pages/groups, Twitter timelines, and Reddit subreddits from Android.

**Problem it solves:** Manual cross-posting is repetitive, error-prone, and slow—especially with multiple brands or regional accounts.

**Benefit:** Consistent, scheduled distribution with tracking, retries, and parallel device execution for 10–1000+ posts per hour (policy-safe pacing).

### Automating Cross-Platform YouTube Video Sharing
- Templates for captions, tags, and UTM parameters keep messaging consistent across platforms.
- Runs on **real devices** or emulators with **non-ADB wireless control** for stealth and stability.
- Built-in scheduler, queues, and per-platform limits to respect rate caps and community rules.
- Central dashboard shows success/fail, retries, and proof logs with screenshots.

## Core Features 

- **Real Devices and Emulators:** Works with physical Android phones and popular emulators (Bluestacks/Nox). Attach one or hundreds; tasks are queued and balanced automatically.
- **No-ADB Wireless Automation:** Appilot’s non-ADB channel controls UI without persistent USB/ADB; fewer disconnects, lower detection surface, and easier rack deployment.
- **Mimicking Human Behavior:** Randomized delays, scroll variance, typing jitter, and UI path variation to resemble natural posting flows on Facebook, Twitter, and Reddit.
- **Multiple Accounts Support:** Manage many brand or regional accounts per platform with safe rotations, cool-downs, and per-account posting caps.
- **Multi-Device Integration:** Run tasks in parallel across device farms; dynamic sharding ensures high throughput with fair scheduling and back-pressure.
- **Exponential Growth for Your Account:** Faster cross-network distribution increases surface area for discovery, boosting link clicks and watch sessions.
- **Premium Support:** Priority onboarding, playbooks for each platform, and rapid incident response with log-based diagnostics.
- **Task Scheduler & Queues:** Cron-like schedules, recurring campaigns, and FIFO/LIFO queues with per-platform concurrency controls.
- **Proxy & Fingerprint Compatibility:** Optional per-device proxies and browser stack settings for hybrid flows (e.g., OAuth handoffs, link previews).
- **Audit Logs & Webhooks:** Structured JSON logs, screenshot evidence, and webhooks to Slack/Discord for success/failure alerts.

### Additional Features
| Feature | Description |
|---|---|
| **Caption Templates & Spintax** | Compose reusable captions with variables (title, shortlink, hashtags) and spintax to reduce repetition. |
| **Link Shortening & UTM** | Auto-shorten video URLs and append UTM parameters for campaign/source tracking. |
| **Per-Platform Rules Engine** | Enforce subreddit flairs, Twitter char limits, and Facebook page/group selection with guardrails. |
| **Retry & Backoff** | Exponential backoff for transient errors; smart requeue with root-cause codes (captcha, rate-limit, network). |
| **Secrets & Vault** | Encrypted storage for credentials/tokens; device-scoped secrets with rotation policies. |
| **Reporting & Exports** | CSV/JSON exports of post results, timestamps, accounts, and device IDs for BI pipelines. |


## How It Works 

1. **Input or Trigger** — From the Appilot dashboard, select the YouTube video (URL/ID), choose target channels (Facebook pages/groups, Twitter accounts, Reddit subs), set captions/templates, and schedule or run now.  
2. **Core Logic** — Appilot drives Android devices/emulators via **UI Automator** or **non-ADB wireless control**, opening apps, navigating to compose screens, pasting templated captions, attaching thumbnails (optional), and submitting posts.  
3. **Output or Action** — Posts are published across selected platforms; the system captures permalinks (where possible), screenshots, and result codes, and can trigger webhooks or follow-up tasks.  
4. **Other functionalities** — Built-in retries, error tagging, structured logging, and parallel processing across a device pool ensure stable throughput and traceability.

## Tech Stack 

- **Language:** Kotlin, Java, Python, JavaScript  
- **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber  
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks, Nox Player, Scrcpy, Firebase Test Lab, MonkeyRunner, Accessibility  
- **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure

    youtube-auto-sharing-bot/
    │
    ├── android/
    │   ├── app/                         # Kotlin service for device orchestration
    │   └── ui-automator/                # UIAutomator flows per platform
    │
    ├── automation/
    │   ├── flows/
    │   │   ├── facebook_post_flow.py
    │   │   ├── twitter_post_flow.py
    │   │   └── reddit_post_flow.py
    │   ├── scheduler/
    │   │   ├── cron_jobs.py
    │   │   └── queue_worker.py
    │   └── utils/
    │       ├── humanizer.py
    │       ├── device_pool.py
    │       ├── templates.py
    │       └── secrets_vault.py
    │
    ├── config/
    │   ├── accounts.yaml                # Mapped accounts per platform
    │   ├── devices.yaml                 # Device/emulator definitions
    │   ├── campaigns.yaml               # Scheduled campaigns
    │   └── settings.yaml                # Global limits, concurrency, proxies
    │
    ├── dashboards/
    │   ├── api/
    │   │   ├── server.ts
    │   │   └── webhooks.ts
    │   └── web/
    │       ├── pages/
    │       │   └── index.tsx
    │       └── components/
    │           └── JobsTable.tsx
    │
    ├── media/
    │   └── appilot-banner.png
    │
    ├── logs/
    │   ├── runs/
    │   │   └── 2025-10-30T15-00Z.log
    │   └── screenshots/
    │       ├── fb_2025-10-30_1501.png
    │       └── tw_2025-10-30_1501.png
    │
    ├── output/
    │   ├── reports.csv
    │   └── posts.json
    │
    ├── scripts/
    │   ├── seed_demo_data.py
    │   └── device_health_check.py
    │
    ├── requirements.txt
    ├── package.json
    └── README.md


## Use Cases 

- **Creators & Agencies** use it to auto-share every new YouTube upload to FB/Twitter/Reddit, so they can maximize reach without manual posting.  
- **Brands with Regional Accounts** use it to push localized captions across multiple profiles, so they can keep messaging consistent and on-time.  
- **Community Managers** use it to schedule Reddit announcement posts with correct flairs, so they can meet subreddit rules reliably.  
- **Newsrooms** use it to syndicate shorts to multiple social handles quickly, so they can hit trending windows.  

## FAQs

**How do I configure this automation for multiple accounts?**  
Define accounts in `config/accounts.yaml` with per-platform credentials and assign them to campaigns. The scheduler rotates accounts with safe cool-downs and caps.

**Does it support proxy rotation or anti-detection?**  
Yes—set device- or account-level proxies in `settings.yaml`. Fingerprint and network settings are applied per device; hybrid browser handoffs are supported where needed.

**Can I schedule it to run periodically?**  
Absolutely. Use `campaigns.yaml` to define cron-like schedules per platform, with per-account posting limits and time-of-day windows.

**What about subreddit rules and flairs?**  
The rules engine validates character limits, required flairs, and NSFW flags before posting, failing fast with actionable error codes.

**Can it attach thumbnails or use shortened links?**  
Yes—upload local thumbnails where supported and auto-shorten URLs with UTM tagging for analytics.

## Performance & Reliability Benchmarks

- **Execution Speed:** Typical end-to-end post in 18–35s per platform per device (including app launch, compose, and confirmation) under normal network conditions.  
- **Success Rate:** **95%** successful posts across platforms in steady-state runs with retry/backoff enabled.  
- **Scalability:** Horizontally scales from a single phone to **300–1000** devices with queue-based sharding and per-device concurrency control.  
- **Resource Efficiency:** Lightweight workers (~150–250MB RAM per device agent); CPU bounded primarily by emulator density and screenshot capture.  
- **Error Handling:** Structured error taxonomy (rate-limit, captcha, network, auth); exponential backoff, circuit breakers, and automatic requeue; screenshot + log bundles for every failure.

 ##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>
