# Inconsistent pricing across pages — dev spec
Site: wedibox.com · Priority 6 · Urgent · Effort: Medium (2-5 days)

## Problem
The homepage and pricing page show conflicting price points for the same product, undermining clarity of cost.

## Evidence (from the live site)
> Prices shown on the page: $49 $49 $49
> Prices shown on the page: $29 $79 $49 $0 $29 $49

## Current state
notes: Conflicting prices across pages

## Required change
notes: Align pricing displays across all pages

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Align pricing displays across all pages
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_inconsistent_pricing_across_pages` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
