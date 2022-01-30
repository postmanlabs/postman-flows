# Send Request

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.09.1 | Added in v21.09.1 |

===

The **Send Request** block can be used to send one of the requests defined in a collection inside the current workspace.
This is block optionally accept a Record in its variable port and uses it to generate data-variable to satisfy the variables used within the selected Request.

+++ Input
| Port                                              | Symbol      | Description                                                                                                                                                     |
| ------------------------------------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Variables [!badge text="optional" variant="info"] | `variables` | Accepts a `Record` containing key value pairs which will be converted to the variables. Nested Records will be [flattened](https://www.npmjs.com/package/flat). |
+++ Output
| Port     | Symbol     | Description                                                                                                                             |
| -------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Response | `response` | Emits a `Record` of the response received for this request                                                                              |
| Test     | `test`     | Emits a `List` of all the tests that were executed for this request. No list will be emitted if the request does not contain any tests. |
+++

||| `response` Schema
```yaml
response: Record
  body: string
  headers: Map
    {key}: string
  http: Record
    statusCode: number
    statusMessage: string
    version: string
    responseTime: number
```
||| `test` Schema
```yaml
test: List
  - {element}: Record
      index: number
      name: string
      passed: bool
      skipped: bool
      [error]: Record (Optional)
        actual: string
        expected: string
        message: string
```
|||