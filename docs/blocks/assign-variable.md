# Assign Variable
[!badge text="Deprecated" variant="warning"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 21.12.2 | Deprecated        |
| 21.10.3 | Added in v21.10.3 |
</details>

!!!warning Deprecated
Use `Send Request` blocks `Assign value to variable` feature to set variable values instead.
!!!

The **Assign variable** can be used to take any type of input data and convert it to a `Map` containing strings as values, that can be used as a data-variable. The assign variable block is not capable of defining constant string values. If string values are needed the [Create Variable](#Create-Variable) block can be used in conjunction with the [Merge](#Merge) block. 

> Note: Nested records are not supported, the values of the records can only be strings or values that can be casted to a string.

+++ Input
| Port | Symbol | Description              |
| ---- | ------ | ------------------------ |
| Data | `data` | Accepts any type of data |
+++ Output
| Port      | Symbol      | Description                                                                                     |
| --------- | ----------- | ----------------------------------------------------------------------------------------------- |
| Variables | `variables` | Emits a `Map<string, string>` which can be used to generate variables in a *Send Request* block |
+++


