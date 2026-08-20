# Pricing page lacks plan selector — dev spec
Site: wedibox.com · Priority 8 · Medium · Effort: Medium (2-5 days)

## Problem
The pricing page lists multiple prices but offers no interactive plan selector or comparison toggle, forcing visitors to parse the page manually to choose a plan.

## Evidence (from the live site)
> One-Time Pricing
> Plans for Couples
> Prices shown on the page: $29 $79 $49 $0 $29 $49

## Current state
notes: No interactive selector

## Required change
notes: Add clickable plan selector or side-by-side comparison table

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add clickable plan selector or side-by-side comparison table
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_page_lacks_plan_selector` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
