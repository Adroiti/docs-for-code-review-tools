Pattern: Useless else on loop

Issue: -

## Description

Loops should only have an else clause if they can exit early with a break statement, otherwise the statements under else should be on the same scope as the loop itself.