# Create Variable
[!badge text="Deprecated" variant="warning"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 21.12.2 | Deprecated        |
| 21.09.1 | Added in v21.12.2 |
</details>

!!!warning Deprecated
Use `Send Request` blocks `Assign value to variable` feature to set variable values instead.
!!!

The *create variable* block can be used define a `Map` containing constant string values. 

> Note: Nested records are not supported, the values of the records can only be strings or values that can be casted to a string.

+++ Input
| Port    | Symbol    | Description                                      |
| ------- | --------- | ------------------------------------------------ |
| Trigger | `trigger` | Accepts any type of data to trigger the creation |
+++ Output
| Port      | Symbol      | Description                                                                                     |
| --------- | ----------- | ----------------------------------------------------------------------------------------------- |
| Variables | `variables` | Emits a `Map<string, string>` which can be used to generate variables in a *Send Request* block |
+++
