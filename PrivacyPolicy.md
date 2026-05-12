---
layout: default
title: Privacy Policy
---

# Privacy Policy — Go Inward Out

**Last updated:** May 12, 2026

Go Inward Out is a private journal for inner experiences — dreams, meditations, mystical experiences, and the like — augmented with AI-assisted reflection. This policy describes what data the app collects, how it's used, and what control you have over it.

The short version, in plain language:

- **Your captures stay yours.** Journal entries, voice recordings, images, and reflections are end-to-end encrypted before they leave your device.
- **The server cannot read your content.** Even our hosting provider (Supabase) sees only ciphertext for your private records.
- **AI processing is initiated by you.** When you tap "Cast a Reading" or similar, the relevant content is sent to Anthropic's Claude API. Anthropic does not use your content to train future models per their API terms.
- **No third-party tracking.** No analytics SDKs, no advertising IDs, no user fingerprinting. The app does not track you across apps or websites.
- **You can export or delete everything at any time.**

---

## 1. What data we collect

### Data you create
- **Captured experiences** — text, voice transcripts, optional images. Stored end-to-end encrypted.
- **Reflections and recasts** — your responses to the Lantern's readings. Stored end-to-end encrypted.
- **Profile information** — name, optional birth data (for astrological context), preferences. Stored end-to-end encrypted.
- **Audio recordings** — original voice files. Stored on-device; sync optional, end-to-end encrypted.

### Data the app needs to function
- **Account identifier** — when you sign in (Apple, Google, or email), the provider returns a stable user ID. We use this to retrieve your encrypted records on a new device.
- **Session token (JWT)** — issued by Supabase Auth, expires periodically, used for authentication.
- **Sync metadata** — timestamps and identifiers of your records (not their contents) so devices can stay synchronized.
- **Device identifier** — a randomly-generated UUID stored on your device, used to disambiguate sync between multiple devices.

### Data the app does NOT collect
- No advertising identifiers (IDFA, GAID, etc.)
- No location data (your birth location, if entered, is treated as profile data and end-to-end encrypted)
- No contacts, calendar, or social-graph data
- No health or biometric data (Face ID happens entirely on-device — Apple does not share the biometric template with the app)
- No browsing history or third-party cookies
- No microphone access without explicit user action (you press to record)

---

## 2. How AI processing works

When you request AI assistance (a reading, a synthesis, voice cleanup, etc.), the following occurs:

1. The relevant content (the experience you wrote, plus context the Lantern needs) is decrypted on your device.
2. It is sent over HTTPS to a Supabase Edge Function we operate.
3. The Edge Function relays it to Anthropic's Claude API (`api.anthropic.com`).
4. Claude returns a response — a reading, a structured analysis, or cleaned text.
5. The response is encrypted and stored back in your records.
6. The plaintext content is **not** retained on the server beyond the lifetime of the request.

Anthropic's API terms (as of this policy's publication) state that prompts and responses are not used to train future models. We retain no plaintext content beyond the request itself; only the structured response is persisted, end-to-end encrypted.

You can disable AI processing entirely from Settings. With AI disabled, Go Inward Out is a pure private journal — no API calls are made.

---

## 3. End-to-end encryption (E2EE)

When you create an account, your device generates a User Master Key (UMK). This key never leaves your device unencrypted.

- Every private record (entry, reflection, recast, profile, etc.) is encrypted with a per-record key generated at write time.
- The per-record key is encrypted ("wrapped") under your UMK before being uploaded.
- The UMK travels between your devices via a one-time pairing code or an optional passphrase-encrypted backup. We never see the plaintext UMK.
- If you choose **not** to back up your UMK and you lose your only device, your records become unrecoverable — by design. This is the privacy tradeoff. We surface this clearly during onboarding.

---

## 4. What the server can see

The server sees:
- Your account ID and authentication tokens
- Encrypted blobs (which it cannot decrypt)
- Timestamps and record identifiers (`created_at`, `updated_at`, etc.) used for sync ordering
- Soft-delete flags

The server cannot see:
- The content of any private record
- Your name, journal text, voice transcripts, images, audio
- Patterns in your inner life
- Anything that would let it profile you, target you, or distinguish you from any other E2EE user

---

## 5. Data sharing with third parties

We share data with these third parties — and only these:

- **Supabase** (our hosting + database provider): receives encrypted blobs and authentication tokens. Cannot decrypt content.
- **Anthropic** (Claude API): receives the contents of an AI request (decrypted on your device) only when you trigger one. Bound by their Commercial Terms — no training on user data.
- **Apple / Google** (auth providers): when you sign in, their token issuance is between you and them; we receive only the resulting auth identifier.

We do not share data with:
- Advertisers
- Analytics vendors
- Data brokers
- Any third party who profiles users for behavioral targeting

---

## 6. Data retention and deletion

- Records you create persist as long as your account exists.
- When you delete a record, it is soft-deleted immediately and hard-deleted from our servers within 30 days.
- When you delete your account (Settings → Delete Account), all server-side records are scheduled for hard deletion within 30 days. Audio blobs and images are removed with the same schedule.
- You can export your full data set as a `.zip` archive at any time (Settings → Export). The archive includes decrypted content and your UMK in plain text — keep it safely.

---

## 7. Your rights

Depending on where you live, you may have rights under GDPR (EU/UK), CCPA (California), or similar regimes:

- **Access:** request a copy of your data — use Settings → Export to do this directly without contacting us.
- **Correction:** edit any record from within the app.
- **Deletion:** delete records or your full account from Settings.
- **Portability:** the export `.zip` is a standard format you can re-import or take elsewhere.
- **Objection / restriction:** contact us using the email below.

We don't sell or share data for cross-context behavioral advertising — nothing to opt out of.

---

## 8. Children

Go Inward Out is not intended for users under 13. If you believe a child has used the app, contact us and we will delete their account and any associated data.

---

## 9. Security

- E2EE for all private content (AES-256-GCM)
- TLS 1.3 for all network traffic
- Supabase Row-Level Security (RLS) so a leaked token from one user cannot read another user's records
- No passwords stored — auth uses Apple, Google, or magic-link email; no password to leak
- Audit logs of API transmissions visible from Settings → Privacy

If you believe you've found a vulnerability, please email the contact below.

---

## 10. Changes to this policy

If we change this policy materially, we'll surface a notice in the app on next launch. The "Last updated" date at the top will change accordingly. Substantive changes will be summarized in the in-app notice.

---

## 11. Contact

Email: **goinwardout@gmail.com** (subject line "Privacy")

GitHub issues: <https://github.com/utahbiker/go-inward-out/issues>

---

*Go Inward Out is built by an independent developer. The app is not affiliated with Anthropic, Apple, or any of the named third parties beyond the contractual relationships described above.*
