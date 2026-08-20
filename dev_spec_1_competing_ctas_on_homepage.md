# Competing CTAs on homepage — dev spec
Site: wedibox.com · Priority 1 · High · Effort: Medium (2-5 days)

## Problem
The homepage presents multiple equally prominent CTAs pointing to different destinations, making the primary next step ambiguous for new visitors.

## Evidence (from the live site)
> 11 distinct calls to action compete on the same page: “Contact Us We are here to help”, “Get Started Free”, “Find Your Seat”, “Contact Us”, “Explore RSVP Tool →”, “Explore Digital Seating Chart →”, “Explore Wedibox Embed →”, “Try Free Demo”.

## Current state
cta: Multiple equally prominent CTAs; notes: Ambiguous primary next step

## Required change
cta: One primary CTA above the fold (e.g., Get Started Free); notes: Visually subordinate secondary links

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Visually subordinate secondary links
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_ctas_on_homepage` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
