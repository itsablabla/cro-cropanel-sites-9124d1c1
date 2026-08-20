# Comparison page omits trust indicators — dev spec
Site: wedibox.com · Priority 9 · Medium · Effort: Medium (2-5 days)

## Problem
The competitor comparison page focuses solely on price and features without any trust or credibility signals for Wedibox, weakening its position against alternatives.

## Evidence (from the live site)
> What Wedding Photo Sharing Apps Actually Cost in 2026
> Price Comparison Table

## Current state
notes: No trust signals

## Required change
notes: Add trust section with rating, wedding count, testimonials

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add trust section with rating, wedding count, testimonials
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_comparison_page_omits_trust_indicators` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
