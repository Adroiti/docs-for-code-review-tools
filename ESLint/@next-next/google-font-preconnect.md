Pattern: Missing use of preconnect resource hint

Issue: -

## Description

A preconnect resource hint was not used with a request to the Google Fonts domain. Adding `preconnect` is recommended to initiate an early connection to the origin.

### Possible Ways to Fix It

Add `rel="preconnect"` to the Google Font domain `<link>` tag:

```jsx
<link rel="preconnect" href="https://fonts.gstatic.com" />
```

## Further Reading

* [next.js - Google Font Preconnect](https://nextjs.org/docs/messages/google-font-preconnect)