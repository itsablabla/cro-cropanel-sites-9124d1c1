# Unclear what $49 buys — dev spec
Site: wedibox.com · Priority 3 · Medium · Effort: Medium (2-5 days)

## Problem
The homepage lists a $49 price without stating which plan or features it corresponds to, leaving visitors uncertain about the offer above the fold.

## Evidence (from the live site)
> Prices shown on the page: $49 $49 $49
> The page's main headline reads “One Wedding QR Code for Collecting Photos , Videos , Messages , Voicemails , RSVPs , and Seating ”.

## Current state
h1: One Wedding QR Code for Collecting Photos , Videos , Messages , Voicemails , RSVPs , and Seating .; notes: $49 price without plan context

## Required change
notes: Add line specifying which plan $49 refers to and what it includes

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add line specifying which plan $49 refers to and what it includes
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unclear_what_49_buys` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
