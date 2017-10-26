Pattern: `csrf` middleware setup before `method-override`

Issue: -

## Description

Detects Express `csrf` middleware setup before `method-override` middleware. This can allow `GET` requests (which are not checked by `csrf`) to turn into `POST` requests later.