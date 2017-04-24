Pattern: Attempted relative import beyond top-level package

Issue: -

## Description

Used when a relative import tries to access too many levels in the current package. For instance, if a package has X levels, trying to climb X + n levels with a relative
import, as in `from ..stuff import Stuff`, will result in an error.
