# Google Play submission — WojakCoin Wallet

Ready-to-paste content and answers for publishing `cash.wojakcoin.wallet` to the
Google Play Store. Pair this with the signed **`app-release.aab`** attached to each
release (the build workflow produces it automatically when signing secrets are set).

- **Package:** `cash.wojakcoin.wallet`
- **Privacy policy:** https://wojakcoin.cash/androidprivacy
- **Contact:** wojakcoin2017@gmail.com
- **Category:** Finance

---

## A. Store listing

**App name (≤30):**

    WojakCoin Wallet

**Short description (≤80):**

    Non-custodial WojakCoin (WJK) wallet. Your keys, your coins. Send, receive, scan.

**Full description (≤4000):**

    WojakCoin Wallet is the official, non-custodial wallet for the WojakCoin (WJK) network. Your private keys and recovery phrase are generated and stored only on your device — we never hold your funds and there is no account to create.

    Features:
    • Self-custody — your keys and recovery phrase stay on your device
    • Send and receive WJK quickly with low fees
    • QR code scanning for addresses and payment requests
    • Multi-language interface
    • View balances and transaction history
    • Bridge support — move WJK to wWojakcoin on Base-ETH and back

    WojakCoin is a fair-launch, proof-of-work cryptocurrency (SHA-256) with no premine. This wallet is open source.

    Important: This is a self-custody wallet. You are responsible for backing up your recovery phrase. If you lose it, your funds cannot be recovered by anyone. WojakCoin Wallet does not buy, sell, or exchange cryptocurrency and does not provide financial advice.

    Privacy: The app collects no personal data and contains no ads or trackers. See our privacy policy: https://wojakcoin.cash/androidprivacy

---

## B. Data safety form

**Collects or shares user data:** No.

Rationale (verified against `package.json`): the app contains **no analytics,
crash-reporting, advertising, or tracking SDKs**. There is no account and no login.
Private keys and the recovery phrase never leave the device (OS backup is disabled).

- All data encrypted in transit: **Yes** (HTTPS).
- Data deletion request method: **N/A — no data collected.**
- Data types (Location, Personal info, Financial info, Messages, Photos, Contacts,
  etc.): **None collected, none shared.**
- Camera: declared as a permission/feature for on-device QR scanning; no image/video
  is stored or transmitted — not "data collection."

**Confirm before submitting:** the app makes network requests to the project's own
services for wallet functionality:
- `https://api.wojakcoin.cash` — balances, fees, transaction broadcast
- `https://explorer.wojakcoin.cash` — blockchain lookups

These receive the requesting IP and the public addresses queried (inherent to any
blockchain app). The "No data collected" answer holds **as long as those servers do
not store/log user-identifying data beyond ephemeral request handling.** If they keep
access logs tied to addresses, declare "Financial info → other" accordingly. The
external exchange/DEX URLs in the app (Komodo, Gleec, Klingex, NestEx, etc.) are
outbound links the user taps, not data collection.

---

## C. Financial features declaration

- Provides financial features: **Yes** → **Cryptocurrency wallet (software / non-custodial).**
- Custodial: **No** — users hold their own keys; the app never takes custody of funds.
- Facilitates buying/selling/exchange/trading of crypto: **No** (send/receive/self-custody
  only; the bridge is a self-custody transfer, not an exchange).
- Licensing/registration: none required for a non-custodial software wallet that does
  not operate an exchange.

---

## D. Content rating (IARC questionnaire)

- Category: Utility / Finance.
- Violence / sexual content / language / controlled substances: **No** to all.
- It is a cryptocurrency wallet (no in-app purchase of digital goods).
- Expected result: **Everyone / PEGI 3**.

---

## E. App access (instructions for reviewers)

    No account or login is required. On first launch, create a new wallet or import
    one using a recovery phrase. All features are available without any special access.
    For testing, create a new wallet — no funds are required to navigate the app.

---

## F. Target audience & content

- Target age: **18+** (do not include under-18 brackets — financial app).
- Appeals to children: **No.**

---

## G. Build & upload

1. The signed `app-release.aab` is attached to each release (built by
   `.github/workflows/build-android.yml` via `bundleRelease` when signing secrets exist).
2. Upload that `.aab` to the Play Console; enroll in **Play App Signing**.
3. Bump `versionCode` (and `versionName`) for every subsequent upload.
