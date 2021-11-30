Pattern: Use of inline script for Google Analytics

Issue: -

## Description

An inline script was used for Google analytics which might impact your webpage's performance.

#### Possible Ways to Fix It

If you are using the `gtag.js` script to add analytics, use the `next/script` component with the right loading strategy to defer loading of the script until necessary.

```js
import Script from 'next/script'

const Home = () => {
  return (
    <div class="container">
      <!-- Global site tag (gtag.js) - Google Analytics -->
      <Script
        src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"
        strategy="afterInteractive"
      />
      <Script id="google-analytics" strategy="afterInteractive">
        {`
          window.dataLayer = window.dataLayer || [];
          function gtag(){window.dataLayer.push(arguments);}
          gtag('js', new Date());

          gtag('config', 'GA_MEASUREMENT_ID');
        `}
      </Script>
    </div>
  )
}

export default Home
```

If you are using the analytics.js script to add analytics:

```js
import Script from 'next/script'

const Home = () => {
  return (
    <div class="container">
      <Script id="google-analytics" strategy="afterInteractive">
        {`
          (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
          (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
          m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
          })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

          ga('create', 'UA-XXXXX-Y', 'auto');
          ga('send', 'pageview');
        `}
      </Script>
    </div>
  )
}

export default Home
```

## Further Reading

* [next.js - Next Script for Google Analytics](https://nextjs.org/docs/messages/next-script-for-ga)