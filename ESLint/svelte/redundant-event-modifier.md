Pattern: Redundant `event` modifier

Issue: -

## Description

Rule #1: Touch event handlers that don't use the `event` object are passive by default.
Rule #2: The passive modifier only works with wheel and touch events.