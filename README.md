[Safari Memory Issue] Memory Spikes and Crashes the browser

How do you use Sentry?
Sentry Saas (sentry.io)

Which SDK are you using? If you use the CDN bundles, please specify the exact bundle (e.g. bundle.tracing.min.js) in your SDK setup.
Sentry Browser CDN bundle

SDK Version
n/a

Framework Version
n/a

Link to Sentry event
n/a

SDK Setup
No response

Steps to Reproduce
For certain implementations of the JS bundle loaded from a CDN, the SDK will crash Safari.

Annecdotally the following has been reported:

[...] seem to have isolated the issue down to circular error handler calls, and the call stack seems to be bouncing between [the] error logging JS and the Sentry SDK

This has been replicated on the following Safari versions when using https://browser.sentry-cdn.com/6.19.7/bundle.min.js:

Version 14.1.2 (16611.3.10.1.16)
Version 16.3 (18614.4.6.1.6)

Please see linked example in synced Jira ticket for a live reproduction.

Expected Result
SDK does not consume memory and crash the browser.

Actual Result<br/>
<img width="511" alt="231545453-f60a5862-4ac0-440a-ac08-08ba09c4dca6" src="https://github.com/user-attachments/assets/cd7f8b24-6914-4c02-9aa5-6e068a92ef5e" />
