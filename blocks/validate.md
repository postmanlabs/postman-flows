### Validate
Stage: [!badge text="Deprecated" variant="warning"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 21.11.1 | Deprecated        |
| 21.09.1 | Added in v21.09.1 |
</details>

!!!warning Deprecated 
Use **Condition** block to conditionally pass data to the next block instead.
!!!

The *Validate* block is a conditional flow control block that routes a data packet to either the `true` port or `false` port based on condition. This block uses some information present within the data itself to perform the validation check.

+++ Input
| Port          | Symbol  | Description               |
| ------------- | ------- | ------------------------- |
| Data (`data`) | `input` | Accepts any type of data. |
+++ Output
| Port  | Symbol  | Description                                       |
| ----- | ------- | ------------------------------------------------- |
| True  | `true`  | Emits the accepted data if the validation passes. |
| False | `false` | Emits the accepted data if the validation fails.  |
+++
