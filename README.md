# Website Privacy & Tracking Audit

> A GDPR / ePrivacy audit of a German direct-to-consumer e-commerce store, focused on cookie consent and pre-consent tracking.

## Overview

I audited a live German e-commerce website to check whether its cookie and tracking behaviour complies with GDPR and ePrivacy (TDDDG) rules. Using only passive, client-side observation, I tested what trackers load before consent, inventoried the cookies set, and assessed the consent banner's design. The audit found that analytics and advertising trackers fire before any consent is given — despite a banner that presents those categories as off by default.

## Skills demonstrated

- GDPR & ePrivacy / TDDDG compliance analysis
- Cookie and third-party tracker auditing
- Consent-mechanism assessment against EDPB dark-pattern guidance
- Translating technical findings into clear, prioritized remediation

## Tools used

Chrome DevTools (Application & Network panels), Blacklight (The Markup), Webbkoll

## What I did

1. Ran automated privacy scans (Blacklight, Webbkoll) for a baseline.
2. Loaded the site in a clean incognito session with DevTools open and recorded which trackers fired *before* interacting with the consent banner.
3. Inventoried the cookies set and categorized them (necessary / analytics / marketing).
4. Assessed the consent banner against valid-consent requirements.
5. Wrote a prioritized findings report with remediation.

## Key findings

- **High —** Non-essential analytics & advertising trackers (Google Analytics, Google Ads, Meta Pixel, Microsoft Clarity incl. session recording, Klaviyo, Shopify analytics) set cookies *before* any consent was given.
- **High —** No "Reject all" option on the first-layer banner; refusing requires an extra step while accepting is one click.
- **Low–Medium —** "Accept all" is visually emphasized over "Reject all," nudging users toward consent.

## Recommendations

- Gate all non-essential tags behind consent (e.g. Google Consent Mode + proper CMP blocking) so nothing fires before opt-in.
- Add an equally prominent "Reject all" button to the first-layer banner.
- Give "Reject all" and "Accept all" equal visual weight.

## What I learned

The most striking lesson was the gap between how a consent banner *looks* and what it actually *does*: the granular toggles defaulted to "off," yet the trackers ran anyway, making the controls partly cosmetic. It reinforced that privacy compliance has to be verified by observing real behaviour, not by trusting the interface.

## Files in this repo

- `report.pdf` — full audit write-up
- `screenshots/` — supporting evidence (cookie values redacted)

## Disclaimer / ethics

This audit used only passive, client-side observation of what a normal visitor's browser receives. No systems were scanned, accessed, or logged into. The target company has been anonymized, and all cookie values (unique identifiers / personal data) have been redacted from the evidence.

---

**Author:** Norbert Eigner — [LinkedIn](https://www.linkedin.com/in/norbert-eigner/)
