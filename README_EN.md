<div align="center">

# 🔄 Life Restart

### An AI-Powered Life Reset System Based on Dan Koe's Periodic Reset Theory

[![WeChat Mini Program](https://img.shields.io/badge/Platform-WeChat_Mini_Program-07C160?logo=wechat&logoColor=white)](https://developers.weixin.qq.com/miniprogram/dev/framework/)
[![Cloud Development](https://img.shields.io/badge/Backend-WeChat_Cloud_Base-4A90D9?logo=icloud&logoColor=white)](https://developers.weixin.qq.com/miniprogram/dev/wxcloud/basis/getting-started.html)
[![DeepSeek](https://img.shields.io/badge/AI-DeepSeek-4A90D9)](https://platform.deepseek.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Most people don't need more motivation — they need a system.** — Dan Koe

[Features](#-features) · [Quick Start](#-quick-start) · [Project Structure](#-project-structure) · [Tech Architecture](#-tech-architecture) · [Deployment](#-deployment-guide)

</div>

---

## 📖 About

**Life Restart** is a WeChat Mini Program based on renowned personal development thinker **Dan Koe**'s "Periodic Reset" theory. It's not another habit tracker or motivational collection — it's a complete **life reset operating system**. From AI diagnosis to action selection, from 6-month boss battles to identity evolution, it helps users transform from **Seeker → Practitioner → Awakener**.

### 🧠 Dan Koe's Periodic Reset Theory

| Concept | Description |
|---------|-------------|
| **Periodic Reset** | Life isn't linear upgrades — proactively "reset" every 6 months: clear old inertia, rebuild new systems |
| **4D Engine** | Health, Wealth, Relationships, Mindset — advance all four dimensions simultaneously |
| **Leverage Actions** | Find the 20% key actions that drive 80% of life change — not doing more, doing the *right* things |
| **Identity Reshaping** | Not "get better" but "switch to a new operating system" — Seeker → Practitioner → Awakener |
| **One-Person Company** | Treat yourself as a company — CEO, Product, Marketing, Finance — all you |

---

## ✨ Features

### 🎮 Core Flow

```
Login → Onboarding → AI 5-Stage Diagnosis → Diagnostic Results → MBTI Test → Action Shop (choose 5-8 of 84)
  → Mode Selection → AI Generates 6-Month Plan → Plan Preview → Daily Check-in → Identity Evolution
```

### 🔥 Key Features

| Module | Feature | Description |
|--------|---------|-------------|
| 🧠 AI Deep Diagnosis | 5-stage deep scan | Health/Wealth/Relationships/Mindset/Lifestyle — pinpoint where you're stuck |
| ⚡ Action Shop | 84 leverage actions | 7 categories, shop like Taobao — pick 5-8 and start immediately |
| ⚔️ 6-Month Boss Battle | Gamified planning | One core boss goal per month, daily tasks, visible progress tracking |
| ✅ Daily Check-in | Habit building | Calendar view + quick check-in + completion rate tracking |
| 🧬 Identity Evolution | 3-level evolution | Seeker → Practitioner → Awakener, 5-dimension skill tree + XP system |
| 👁️ Mentor Zero | Smart interactive coach | Encourage/supervise/celebrate/fun — more direct than besties, more effective than affirmations |
| 🎓 Restart Academy | Lesson cards + 7-day challenge | Theory learning + scenario simulator |
| 🌙 Night Reflection | ORID review method | Vision card/anti-vision/identity declaration/rules list |
| 🔮 Cybernetics Tracker | Radar chart closed loop | Set goals → Act → Measure → Adjust |

### 🎯 84 Leverage Actions by Category

| Category | Count | Sample Actions |
|----------|-------|----------------|
| 💪 Health | 12 | Meditate 10 min, walk 10,000 steps, sleep before 11 PM |
| 💼 Career | 14 | Learn a monetizable skill, start a side project, write professional articles |
| 💕 Relationships | 12 | Meet an old friend, talk to a stranger, write a letter |
| 💰 Finance | 12 | Track expenses for 7 days, save first ¥1000, declutter & sell |
| 🧠 Mindset | 13 | Gratitude journal, do one scary thing, write anti-vision |
| 🏠 Lifestyle | 12 | Build a morning routine, no phone before bed, declutter |
| 🌟 Comprehensive | 12 | 30-day no-quit challenge, life review, design your ideal day |

---

## 🚀 Quick Start

### Prerequisites

- [WeChat DevTools](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) latest stable version
- WeChat Mini Program AppID (register at [WeChat Official Platform](https://mp.weixin.qq.com/))
- WeChat Cloud Base environment (enable in DevTools)
- DeepSeek API Key (for AI generation features)

### Installation Steps

```bash
# 1. Clone the project
git clone https://github.com/your-username/life-script-generator.git
cd life-script-generator

# 2. Open with WeChat DevTools
# Select project directory → enter AppID → confirm

# 3. Enable Cloud Base environment
# Toolbar → Cloud Base → Enable → record environment ID

# 4. Configure Cloud Base environment ID
# Edit miniprogram/app.js, change env to your cloud environment ID
```

### Mock Mode (Preview Locally Without Cloud Base)

```javascript
// miniprogram/app.js
var MOCK_MODE = true;  // Set to true for local preview, no cloud environment needed
```

> Mock mode intercepts all `wx.cloud.callFunction` calls and returns local mock data — ideal for frontend development and debugging.

---

## 📁 Project Structure

```
life-script-generator/
├── miniprogram/                    # Mini Program Frontend
│   ├── app.js                      # Entry file (global state, Mock mode, cloud init)
│   ├── app.json                    # Global config (page routes, TabBar, window styles)
│   ├── app.wxss                    # Global styles
│   ├── sitemap.json                # Sitemap
│   ├── images/                     # Static image assets
│   │   └── tab/                    # TabBar icons
│   ├── styles/
│   │   └── variables.wxss          # Cyber Trend global CSS variables
│   ├── utils/                      # Utility modules
│   │   ├── constants.js            # Constants (84 actions, diagnosis stages, MBTI, etc.)
│   │   ├── mock-cloud.js           # Mock cloud function interceptor
│   ��   ├── auth.js                 # Login authentication
│   │   ├── storage.js              # Local storage wrapper
│   │   └── util.js                 # General utility functions
│   ├── services/                   # Service layer (frontend-backend bridge)
│   │   ├── restart-service.js      # Restart plan service (generate, confirm, local fallback)
│   │   ├── leverage-service.js     # Leverage action service (check-in, calendar, status)
│   │   ├── diagnose-service.js    # Diagnosis service
│   │   ├── mbti-service.js         # MBTI test service
│   │   ├── user-service.js         # User service (login, progress sync)
│   │   ├── interaction-service.js  # Daily interaction service
│   │   ├── reflection-service.js  # Night reflection service
│   │   └── vision-service.js       # Vision card service
│   ├── components/                 # Custom components
│   │   ├── action-card/            # Action card
│   │   ├── boss-card/              # Boss battle card
│   │   ├── boss-hp-bar/            # Boss HP bar
│   │   ├── daily-interaction/      # Mentor Zero popup
│   │   ├── diagnose-step/          # Diagnosis step
│   │   ├── empty-state/            # Empty state placeholder
│   │   ├── interrupt-timeline/     # Interruption timeline
│   │   ├── leverage-action-item/   # Leverage action item
│   │   ├── mbti-progress/          # MBTI progress bar
│   │   ├── progress-bar/           # General progress bar
│   │   └── vision-banner/          # Vision banner
│   └── pages/                      # Pages (28 total)
│       ├── index/                  # 🏠 Home (restart overview + quick check-in)
│       ├── login/                  # Login (WeChat auth + privacy agreement)
│       ├── onboarding/             # New user onboarding (3 steps)
│       ├── restart-diagnose/       # 5-stage AI diagnosis
│       ├── diagnose-result/        # Diagnosis results
│       ├── mbti-test/              # MBTI test
│       ├── mbti-result/            # MBTI results
│       ├── action-shop/            # ⚡ Action shop (choose 5-8 of 84)
│       ├── mode-select/            # Mode selection (pure action / theory + action)
│       ├── generating/             # AI generating (animation)
│       ├── plan-preview/           # Plan preview
│       ├── plan-edit/              # Plan editing
│       ├── leverage-action/        # ⚡ Actions page (calendar + check-in)
│       ├── boss-detail/            # Boss battle details
│       ├── action-detail/          # Action detail + check-in
│       ├── evolution/             # 🧬 Evolution page (skill tree + XP)
│       ├── academy/                # 🎓 Academy
│       ├── lesson-detail/          # Lesson card detail
│       ├── challenge/              # 7-day challenge
│       ├── simulator/             # Scenario simulator
│       ├── night-reflection/       # 🌙 Night reflection
│       ├── vision-card/            # Vision card
│       ├── rules-list/             # Rules list
│       ├── identity-declaration/   # Identity declaration
│       ├── cybernetics-tracker/    # Cybernetics tracker (radar chart)
│       ├── profile/                # 👤 Profile
│       ├── profile-info/           # Personal info
│       ├── settings/               # Settings
│       └── agreement/              # User agreement & privacy policy
├── cloud/                           # Cloud functions
│   ├── script/                     # 📝 Plan generation (AI core)
│   │   ├── index.js                # Entry: generate/save/getDetail/confirm
│   │   ├── ai-client.js            # DeepSeek API client (Node.js https, zero external deps)
│   │   ├── prompts.js              # AI prompt templates
│   │   ├── script-parser.js        # AI response parser
│   │   ├── daily-tasks-builder.js  # Calendar expansion (monthly → daily_tasks)
│   │   ├── fallback.js             # Local fallback plan generation
│   │   └── package.json            # wx-server-sdk only
│   ├── checkin/                     # ✅ Check-in
│   │   └── index.js                # daily/weekly updates daily_tasks, once marks leverage_actions
│   ├── diagnose/                    # 🧠 Diagnosis
│   │   └── index.js                # save/getDetail
│   ├── mbti/                        # 🧬 MBTI
│   │   ├── index.js                # submitTest
│   │   └── questions.js            # MBTI question bank
│   ├── user/                        # 👤 User
│   │   └── index.js                # login/updateProgress/getProgress
│   └── achievement/                 # 🏆 Achievements
│       ├── index.js                # Unlock/query
│       └── rules.js                # Achievement rule definitions
├── docs/                            # Documentation
│   ├── prd-restart-life.md         # PRD v4
│   ├── prd-restart-life-v3.md      # PRD v3
│   ├── architecture-restart-life.md  # Architecture v4
│   ├── architecture-restart-life-v3.md  # Architecture v3
│   ├── class-diagram-v3.mermaid    # Class diagram
│   └── sequence-diagram-v3.mermaid  # Sequence diagram
├── project.config.json              # WeChat DevTools project config
├── package.json                     # NPM package info
├── README.md                        # This file (Chinese)
└── README_EN.md                     # English README
```

---

## 🏗️ Tech Architecture

### Tech Stack

| Layer | Technology | Description |
|-------|-----------|-------------|
| Frontend | WeChat Mini Program Native | WXML + WXSS + JS, no third-party frameworks |
| UI Style | Cyber Trend | Custom CSS variable system, glassmorphism + neon effects |
| Backend | WeChat Cloud Base | Cloud functions + cloud database + cloud storage |
| AI Engine | DeepSeek API | Node.js native https calls, zero external npm dependencies |
| Database | Cloud Database (NoSQL) | 5 collections: scripts, checkins, users, diagnose_results, achievements |

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────┐
│                  WeChat Mini Program Frontend            │
│  ┌──────────┐  ┌──────────┐  ┌──────────────────────┐   │
│  │  Pages    │  │Components│  │      Services        │   │
│  │  (28)     │  │ (11)     │  │   (8 service layers) │   │
│  └────┬─────┘  └────┬─────┘  └────────┬─────────────┘   │
│       │              │                 │                 │
│  ┌────┴──────────────┴─────────────────┴─────────────┐  │
│  │              Utils / Constants                      │  │
│  │    (mock-cloud / auth / storage / constants)        │  │
│  └────────────────────┬───────────────────────────────┘  │
└───────────────────────┼─────────────────────────────────┘
                        │ wx.cloud.callFunction()
┌───────────────────────┼─────────────────────────────────┐
│                 WeChat Cloud Base                        │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌──────────────┐  │
│  │ script │  │ checkin│  │  user  │  │  diagnose     │  │
│  │(AI Gen)│  │(Check) │  │(User)  │  │  (Diagnosis)  │  │
│  └───┬────┘  └────────┘  └────────┘  └──────────────┘  │
│      │                                                    │
│  ┌───┴─────────────────���────────────────────────────┐  │
│  │             Cloud Database (NoSQL)                 │  │
│  │  scripts │ checkins │ users │ diagnose_results     │  │
│  └───────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
                        │
                ┌───────┴───────┐
                │  DeepSeek API  │
                │ (AI Engine)    │
                └───────────────┘
```

### Data Flow

```
User Action → Page → Service → wx.cloud.callFunction → Cloud Function → Cloud Database
                                                     ↓
                                              DeepSeek API (script only)
                                                     ↓
                                        AI Generate → Parse → Store → Return to Frontend
```

### Core Design Patterns

| Pattern | Implementation | Description |
|---------|---------------|-------------|
| **3-Layer Architecture** | Page → Service → Cloud Function | Pages handle UI only, Services encapsulate business logic, Cloud Functions process data |
| **Mock Interceptor** | mock-cloud.js | Intercepts all cloud function calls when `MOCK_MODE=true`, returns local mock data |
| **Local Fallback** | fallback.js + localPlan | Generates plan locally when cloud function fails, uses `local_` prefix ID |
| **Cloud Progress Sync** | setter → `_syncProgressToCloud` | Fire-and-forget sync to cloud after every state change |
| **Login Recovery** | `loadUserDataFromCloud` | Restores all progress data from cloud after re-login |

---

## 🎨 UI Design System

### Cyber Trend Style

A dark-themed design language for Gen Z aesthetics, blending cyberpunk neon + glassmorphism + gamification elements.

#### Color Palette

| Category | Value | Usage |
|----------|-------|-------|
| 🟣 Neon Purple | `#6C5CE7` | Brand primary, buttons, highlights |
| 🩷 Neon Pink | `#FD79A8` | Accent, interaction feedback |
| 🟢 Neon Green | `#00F5A0` | Success state, evolution indicator |
| 🔵 Neon Blue | `#00D2FF` | Info hints |
| 🟡 Neon Yellow | `#F1FA8C` | Creativity skill |
| 🟠 Neon Orange | `#FFB86C` | Warnings, discipline |
| ⬛ Dark Background | `#0F0E17` | Page background |
| 🪟 Glassmorphism | `rgba(30,28,46,0.65)` | Card background |

#### Identity Rank Colors

| Rank | Color | Description |
|------|-------|-------------|
| 🌱 Seeker | `#8B9DC3` | Just starting the restart journey |
| ⚡ Practitioner | `#C9A96E` | Found direction, taking action |
| 🔥 Awakener | `#00F5A0` | System running, continuous evolution |

---

## 🚢 Deployment Guide

### 1. Cloud Base Environment Setup

```bash
# In WeChat DevTools:
# 1. Click 「Cloud Base」→ Create environment
# 2. Record environment ID (e.g., cloud1-xxxxx)
# 3. Edit miniprogram/app.js env field
```

### 2. Cloud Database Collections

Create the following collections in the Cloud Base console:

| Collection | Permission | Description |
|-----------|-----------|-------------|
| `scripts` | Creator-only read/write | Restart plan data |
| `checkins` | Creator-only read/write | Check-in records |
| `users` | Creator-only read/write | User info + progress |
| `diagnose_results` | Creator-only read/write | Diagnosis results |
| `achievements` | Creator-only read/write | Achievement records |

### 3. Cloud Function Deployment

```bash
# In WeChat DevTools:
# 1. Right-click cloud/script → Upload & Deploy: Install Dependencies in Cloud
# 2. Right-click cloud/checkin → Upload & Deploy
# 3. Right-click cloud/diagnose → Upload & Deploy
# 4. Right-click cloud/mbti → Upload & Deploy
# 5. Right-click cloud/user → Upload & Deploy
# 6. Right-click cloud/achievement → Upload & Deploy
```

### 4. Environment Variable Configuration

```bash
# In Cloud Base console → Cloud Functions → script → Configuration:
# AI_API_KEY = your_deepseek_api_key
```

> ⚠️ The `script` cloud function uses Node.js native `https` module to call DeepSeek API — **zero external npm dependencies**, won't crash from `Cannot find module`.

### 5. Disable Mock Mode

```javascript
// miniprogram/app.js
var MOCK_MODE = false;  // MUST turn off for production deployment
```

### 6. Upload & Submit for Review

```bash
# In WeChat DevTools:
# 1. Click 「Upload」→ Enter version number and notes
# 2. Log in to WeChat Official Platform → Version Management → Submit for Review
```

---

## ⚠️ Common Pitfalls

### WeChat Review

| Issue | Solution |
|-------|----------|
| "Login implies consent" rejected | Use explicit checkbox, never imply consent |
| `requiredPrivateInfos` compile error | This field only accepts location-related API names; `chooseAvatar`/`getNickname` cause errors — configure privacy in backend only |
| Privacy popup not working | Add `__usePrivacyCheck: true` in `app.json` |

### WeChat Mini Program CSS

| Issue | Solution |
|-------|----------|
| `flex gap` iOS incompatibility | Use `margin` instead |
| `button` default styles override-resistant | `!important` + `button::after { border: none }` |
| `button` misbehaves in flex containers | Use `display: inline-flex` + fixed padding |
| `max-width: 84vw` too narrow on small screens | Use fixed `rpx` + `min-width` fallback |
| Chinese characters stacking vertically | `white-space: nowrap` + `display: inline-block` |

### Cloud Functions

| Issue | Solution |
|-------|----------|
| `callFunction:fail` = cloud function crash | Usually top-level `require` failure; minimize external npm deps |
| Global try-catch can't catch top-level require | `require` happens before `exports.main` |
| `cloud.database()` breaks entire module | Use lazy `getDB()` initialization |
| Cloud function data format incompatible with frontend | Static content (diagnosis questions, MBTI) uses local constants only, never overwrite with cloud data |

### WXML

| Issue | Solution |
|-------|----------|
| `obj[key]` dynamic access not allowed | Pre-compute flat structures in JS |
| Nested key access not allowed | Pre-compute in step-change callbacks |
| `.join()` not supported | Pre-compute string in JS |
| Objects rendered as `[object Object]` | Defensive conversion on `{text, value}` objects from cloud functions |

### Data Loss

| Issue | Solution |
|-------|----------|
| All data lost after logout | Store progress fields in cloud `users` collection, restore via `loadUserDataFromCloud` on re-login |
| 6 setters don't sync to cloud | Add `_syncProgressToCloud()` (fire-and-forget) at end of each setter |
| Old `current_script_id` incompatibility | Map `current_script_id → current_plan_id` in `loadUserDataFromCloud` |

---

## 🔧 Development Guide

### Mock Mode Development

```javascript
// Enable Mock mode
// miniprogram/app.js
var MOCK_MODE = true;

// In Mock mode:
// - All wx.cloud.callFunction calls intercepted by mock-cloud.js
// - Returns local mock data
// - No cloud environment needed for preview
// - Ideal for frontend UI development and debugging
```

### Adding a New Page

```bash
# 1. Create page directory under miniprogram/pages/
# 2. Register route in miniprogram/app.json pages array
# 3. WeChat DevTools auto-generates .js/.json/.wxml/.wxss quartet
```

### Adding a New Cloud Function

```bash
# 1. Create directory under cloud/
# 2. Write index.js + package.json (wx-server-sdk only)
# 3. Right-click upload and deploy
# 4. ⚠��� Zero external npm dependencies! Use Node.js built-in modules
```

### Adding a New Leverage Action

```javascript
// miniprogram/utils/constants.js → ACTION_OPTIONS
// ID format: two digits (H01/C01/M01/L01/R01/F01/X01)
// Frequency mapping: habit→daily / action+learning+social+income→weekly
```

---

## 🗺️ Product Roadmap

### ✅ Completed (v1.0.0)

- [x] AI 5-stage diagnosis
- [x] MBTI test + result interpretation
- [x] 84 leverage actions shop
- [x] Dual mode (pure action / theory + action)
- [x] AI generates 6-month restart plan
- [x] Calendar view + daily check-in
- [x] Identity evolution system (Seeker → Practitioner → Awakener)
- [x] 5-dimension skill tree + XP system
- [x] Mentor Zero smart interaction
- [x] Restart Academy (lesson cards + 7-day challenge + simulator)
- [x] Night reflection + vision card + identity declaration
- [x] Cybernetics tracker (radar chart closed loop)
- [x] Privacy policy compliance (WeChat review passed)
- [x] Login data persistence (cloud progress sync)

### 🔜 Planned

- [ ] Social sharing (QR code check-in posters)
- [ ] Data dashboard (weekly/monthly statistics charts)
- [ ] Action community (user UGC interaction)
- [ ] Customizable themes (more UI skins)
- [ ] Mini Program cross-promotion
- [ ] Subscription push notifications (check-in reminders)
- [ ] AI conversational coach (multi-turn interaction)

---

## 🤝 Contributing

Contributions of all forms are welcome!

1. **Fork** this repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a **Pull Request**

### Commit Convention

```
feat:     New feature
fix:      Bug fix
docs:     Documentation updates
style:    Style changes (no logic impact)
refactor: Refactoring (neither feature nor bug fix)
perf:     Performance optimization
test:     Testing related
chore:    Build tools / auxiliary changes
```

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

## 🙏 Acknowledgements

- **[Dan Koe](https://thedankoe.com/)** — Periodic Reset theory, leverage actions, identity reshaping, one-person company philosophy
- **[DeepSeek](https://platform.deepseek.com/)** — AI generation engine
- **[WeChat Cloud Base](https://developers.weixin.qq.com/miniprogram/dev/wxcloud/basis/getting-started.html)** — Backend infrastructure

---

<div align="center">

**Most people don't need more motivation — they need a system.**

🔍 Search WeChat for「**重启人生**」→ Start your first reset now

[⬆ Back to Top](#-life-restart)

</div>
