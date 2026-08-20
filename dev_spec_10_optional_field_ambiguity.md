# Optional field ambiguity — dev spec
Site: wedibox.com · Priority 10 · Medium · Effort: Low (0.5-2 days)

## Problem
The get-started form labels one field as optional but does not clarify which fields are required, leaving visitors unsure what they must provide before proceeding.

## Evidence (from the live site)
> Tell us moreoptional

## Current state
notes: Only 'Tell us more' labeled optional

## Required change
notes: Add required-field markers to Partner one, Partner two, Event date

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add required-field markers to Partner one, Partner two, Event date
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_optional_field_ambiguity` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
