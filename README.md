# Safari Memory Issue: Memory Spikes and Browser Crashes

## How to Use Sentry
- **Sentry SaaS**: [sentry.io](https://sentry.io)

## SDK Information
- **SDK Type**: Sentry Browser CDN bundle
- **SDK Version**: n/a
- **Framework Version**: n/a

## Link to Sentry Event
- **Event Link**: n/a

## SDK Setup
- **Response**: No response

## Steps to Reproduce
Certain implementations of the JS bundle loaded from a CDN cause the SDK to crash Safari. Anecdotal reports indicate the issue stems from circular error handler calls, resulting in a call stack that oscillates between the error logging JavaScript and the Sentry SDK.

This issue has been replicated on the following Safari versions when using the CDN link:
- [https://browser.sentry-cdn.com/6.19.7/bundle.min.js](https://browser.sentry-cdn.com/6.19.7/bundle.min.js)
  - **Version 14.1.2** (16611.3.10.1.16)
  - **Version 16.3** (18614.4.6.1.6)

For a live reproduction example, please refer to the linked Jira ticket.

## Expected Result
The SDK should not consume excessive memory or crash the browser.

## Actual Result
![Memory Issue Screenshot](https://github.com/user-attachments/assets/cd7f8b24-6914-4c02-9aa5-6e068a92ef5e)
