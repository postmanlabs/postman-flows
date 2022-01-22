# Check
[!badge text="Experimental" variant="primary"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 21.11.1 | Added in v21.11.1 |
</details>

The **Check** block accepts input from 2 sources and lets you write expressions with the new [Expression input](https://github.com/postmanlabs/postman-flows/discussions/124). 
If the condition resolves to `True` it passes the data through otherwise burns the data away.

+++ Input
| Port      | Symbol      | Description                                                      |
| --------- | ----------- | ---------------------------------------------------------------- |
| Primary   | `primary`   | Data which needs to pass through if condition resolves to `True` |
| Secondary | `secondary` | Other source of data which does not pass through                 |
+++ Output
| Port    | Symbol    | Description                                                                        |
| ------- | --------- | ---------------------------------------------------------------------------------- |
| Primary | `primary` | Passes data received from `Primary` input port if the condition resolves to `True` |
+++


