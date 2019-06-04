# Advizr Engagement Workflow

Advizr Engagement Workflow is a prospecting tool available to current Advizr clients for free. This page will show you how to add the Advizr Engagement Workflow widget to your website. For questions or help, please email support@advizr.com.

The Advizr Engagement Workflow widget supports "responsive" or "mobile optimized" websites, and will resize down to 320px width.

## Installation

Just paste the following code anywhere into your website:

```html
<div id="AdvizrEngagementWorkflow"></div>

<script src="https://resources.advizr.com/engagement/bootstrap.js"></script>
```

## Listening for results

The embeded iFrame will post a message to the parent when results are calculated.
To use them you just need to add the corresponding listener:

```js
window.addEventListener(
  'message',
  event => {
    if (!/\.advizr\.com$/.test(event.origin)) {
      return;
    }

    try {
      const message = JSON.parse(event.data);

      if (message.type === 'FINANCIAL_RESULTS') {
        console.log('Results: ', message.payload);
      }
    } catch (err) {
      console.error(err);
    }
  },
  false
);
```

Don't forget to check for the `event.origin` otherwise you'll be exposed to a security vulnerability.

## Demo

Take a look at [demo](https://resources.advizr.com/engagement/demo.html)

## Help

For questions or help, please email support@advizr.com.
