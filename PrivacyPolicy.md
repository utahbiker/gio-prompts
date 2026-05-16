---
layout: default
title: Privacy Policy
---

# Privacy Policy — Go Inward Out

**Last updated:** May 12, 2026

Go Inward Out is a private journal for inner experiences — dreams, meditations, mystical experiences, somatic states, ordinary days — augmented with AI-assisted reflection through a feature we call **the Lantern**. This policy describes what data we collect, how it's used, and what control you have over it.

## In plain language

- Your captured experiences, voice recordings, transcripts, readings, and reflections are encrypted in transit (TLS) and at rest in our database (Supabase server-side AES-256 encryption).
- We don't read your content. Our systems and our team are designed to keep your data accessible only to you and to the AI services you direct.
- When you tap "Cast a Reading," the relevant content is sent to Anthropic's Claude API to compose a response. Anthropic does not use your content to train future models per their Commercial Terms.
- We use **no** analytics SDKs, **no** advertising IDs, **no** fingerprinting, **no** cross-app or cross-site tracking.
- Sign in (Apple or email magic link) and your data is restored on any device.
- You can export your data or delete your account at any time.

## What we collect

### Data you create

- **Captured experiences** — title, body text, voice transcripts, optional images, your tagging (type, emotions, felt significance, intention).
- **Reflections** and your replies to the Lantern's readings.
- **Profile info** — optional display name, optional birth data, preferences.
- **Audio recordings** — when you capture by voice; transcripts are derived from these on your device.

### Data we need to operate

- **Account identifier** — a stable user ID issued by Supabase. When you sign in with Apple or email, the resulting identity is linked to this ID so your data restores on any device you sign in on.
- **Session tokens** — Supabase issues short-lived JWTs for authenticated requests.
- **Sync metadata** — record IDs, timestamps, deletion markers used to keep your devices in sync.
- **Device identifier** — a random UUID generated locally per app install. Used only for sync envelope identification.

### Data we do **not** collect

- Advertising identifiers (IDFA, GAID, etc.)
- Location, contacts, calendar, health data, browsing history, search history outside the app
- Microphone access only when you press to record. Camera and photo library are not currently used by the app.

## How AI works

When you request AI assistance (cast a reading, generate synthesis, clean up a voice transcript), the relevant content is sent over HTTPS to a Supabase Edge Function we operate. That function relays the request to Anthropic's Claude API and returns the response. The response is stored back in your records.

- Anthropic's Commercial Terms prohibit training on your data.
- Anthropic retains your prompt and response for up to 30 days for safety review, then deletes them.
- You can disable AI entirely from **Settings → AI**. With AI disabled, Go Inward Out functions as a pure private journal — no requests leave the app.

## What our infrastructure sees

- **Supabase** (our hosting + database provider, US-based): your records are encrypted at rest using AES-256 with keys managed by Supabase. Supabase's technical staff have administrative access to our database but contractually agree to access user data only for support tickets you've initiated. We have not configured any database extension or function that would expose your data beyond your own authenticated requests.
- **Anthropic**: receives your prompt (the relevant entry text + context blocks) and returns a response. Bound by Anthropic's Commercial Terms — no training, 30-day retention, then deleted.
- **Apple / email providers**: when you sign in, the provider issues a token bound to your identity. We receive the resulting auth identifier (e.g. the Apple user ID) and your email if you provided it.

We do **not** share data with advertisers, analytics vendors, data brokers, or any party that profiles users for behavioral targeting.

## Where your data lives

All data is processed in the United States by Supabase Inc. Voice transcripts, reading text, and AI requests transit to Anthropic's US-based infrastructure under their Commercial Terms.

If you are an EU/UK resident, you have the rights described in **Your rights** below regarding international transfer.

## Data retention and deletion

- Records you create persist as long as your account exists.
- When you delete a record, it is moved to **Trash** for 30 days, then permanently purged on next sync.
- To delete your account: **Settings → Account → Delete Account**. Server-side data is purged within 30 days. Email `goinwardout@gmail.com` if you need confirmation or a faster purge.
- Export your data anytime: **Settings → Data → Export**.

## Your rights

Regardless of where you live:

- **Access** — Export your data via Settings → Data → Export.
- **Correction** — Edit records in the app.
- **Deletion** — Delete records or your full account from Settings.
- **Portability** — The export is standard JSON; take it elsewhere.
- **Objection** — Email `goinwardout@gmail.com` with concerns or requests.

EU/UK/California residents may have additional rights under GDPR / UK GDPR / CCPA. We honor those requests at the email above.

## Children

Go Inward Out is not directed at users under 13. We do not knowingly collect data from users under 13.

## Security

- TLS 1.2+ for all network traffic
- AES-256 encryption at rest (Supabase-managed)
- Per-user Row-Level Security on every table — a leaked token from one user cannot read another user's records
- No passwords stored. Authentication via Apple Sign-In or email magic link.
- Optional Face ID gate per entry (Settings → Privacy on each entry) and optional App Lock for the entire app (Settings → Security)
- Audit log of AI transmissions visible in Settings → Privacy → Transmissions

## What this policy doesn't promise

We want to be honest about the scope of our commitments:

- We don't claim end-to-end encryption. Your data is encrypted in transit and at rest, but our hosting provider's privileged staff have theoretical technical access — the same posture as nearly every cloud service you use.
- We don't claim zero-trust against Anthropic. When you cast a reading, Anthropic temporarily receives your prompt content; their Commercial Terms govern what they do with it.
- We don't claim immunity from legal compulsion. If lawfully compelled by a court order, we may have to disclose data we hold.

What we do promise: we won't read your data manually for any reason that isn't a support ticket you've initiated. We won't train AI models on your data. We won't sell it. We won't share it with advertisers or analytics vendors.

## Changes

We'll surface material changes in-app. The "Last updated" date at the top changes when we revise this policy.

## Contact

- **Email:** goinwardout@gmail.com
- **GitHub:** https://github.com/utahbiker/go-inward-out/issues (for public-facing technical questions)
