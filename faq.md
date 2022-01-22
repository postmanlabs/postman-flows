---
label: FAQ
icon: question
---

# Frequently Asked Questions :thinking_face:

### Why are my pre-request and test scripts not running in flows? 
Pre-request and tests are actually running in flows, but environment, globals updated
is blocked in flows. The reason for this decision has been explained in the following document.
[!ref Environment update blocked](https://github.com/postmanlabs/postman-flows/discussions/142)

If you add a `console.log` you can see you output in the Postman Console and the results of the tests
can be viewed by using the [Test Summary](./docs/blocks/test-summary.md) block.