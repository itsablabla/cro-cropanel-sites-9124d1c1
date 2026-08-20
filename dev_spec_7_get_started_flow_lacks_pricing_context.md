# Get-started flow lacks pricing context — dev spec
Site: wedibox.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
The get-started page shows prices but emphasizes 'free forever', creating ambiguity about when payment occurs in the funnel.

## Evidence (from the live site)
> Prices shown on the page: $0 $49 $79
> Page copy reads “Create a beautiful, free wedding page — ready in 60 seconds”.
> 2 distinct calls to action compete on the same page: “Sign in”, “See what's included →”.

## Current state
cta: Sign in | See what's included →; notes: Copy emphasizes free, but prices shown

## Required change
cta: Clarify free tier and optional upgrades; notes: State that next step is free

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN State that next step is free
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_get_started_flow_lacks_pricing_context` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
