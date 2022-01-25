# Condition

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.11.1 | Added in v21.11.1 |

===

The **Condition** block lets you write expressions with the new [Expression input](https://github.com/postmanlabs/postman-flows/discussions/124). If the condition resolves to `True` it passes the data through the "Accept" port, and if the expression resolves to `False` it passes the data through "Reject" port

+++ Input
| Port | Symbol | Description                                  |
| ---- | ------ | -------------------------------------------- |
| Data | `data` | Accepts data on which decision is to be made |
+++ Output
| Port   | Symbol   | Description                                               |
| ------ | -------- | --------------------------------------------------------- |
| Accept | `accept` | Passes data received if the condition resolves to `True`  |
| Reject | `reject` | Passes data received if the condition resolves to `False` |
+++


