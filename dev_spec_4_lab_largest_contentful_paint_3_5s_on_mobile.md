# Lab Largest Contentful Paint of 3.5 s on mobile — dev spec
Site: wedibox.com · Priority 4 · Medium · Effort: Medium (2-5 days)

## Problem
Measured in a lab load: the page's main content takes this long to appear on a mid-range phone; most visitors have bounced long before.

## Evidence (from the live site)
> Lighthouse (mobile emulation, single synthetic run via DataForSEO): Largest Contentful Paint 3.5 s against a ‘good’ threshold of 2500ms. Lab data, not real-user field data — confirms the defect class, not the field percentile.

## Current state
notes: Largest Contentful Paint 3.5 s (lab, mobile)

## Required change
notes: Largest Contentful Paint ≤ 2500ms (good)

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Largest Contentful Paint ≤ 2500ms (good)
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_lab_largest_contentful_paint_3_5s_on_mobile` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
