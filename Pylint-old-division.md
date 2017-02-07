Pattern: Old division

Issue: -

## Description

Used for non-floor division w/o a float literal or ``from __future__ import division`` (Python 3 returns a float for int division unconditionally). This message can't be emitted when using Python >= 3.0.