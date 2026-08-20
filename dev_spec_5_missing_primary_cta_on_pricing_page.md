# Missing primary CTA on pricing page — dev spec
Site: wedibox.com · Priority 5 · Urgent · Effort: Medium (2-5 days)

## Problem
The pricing page presents plans and prices but lacks a clear, plan-specific call-to-action, leaving visitors without a direct path to purchase.

## Evidence (from the live site)
> 9 distinct calls to action compete on the same page: “Contact Us We are here to help”, “Get Started Free”, “Find Your Seat”, “Contact Us”, “Explore Embed”, “Start over”, “See supported platforms →”, “See how Wedibox works”.

## Current state
cta: Generic site-wide links; notes: No plan-specific CTA

## Required change
cta: Plan-specific primary CTA button beneath each pricing tier; notes: Leads to checkout or get-started flow

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Leads to checkout or get-started flow
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_primary_cta_on_pricing_page` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
