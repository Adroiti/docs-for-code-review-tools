Pattern: Unsupported browser feature

Issue: -

## Description

Disallow features that aren't supported by target browser audience.

This rule checks if the CSS you're using is supported by the browsers you're targeting. It uses doiuse to detect browser support. Doiuse itself checks your code against the caniuse database and uses browserslist to get the list of browsers you want to support. Doiuse and this plugin are only compatible with standard css syntax, so syntaxes like scss, less and others aren't supported.

## Further Reading

* [stylelint-no-unsupported-browser-features](https://github.com/ismay/stylelint-no-unsupported-browser-features)