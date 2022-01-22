# Start 
[!badge text="Experimental" variant="primary"]

<details>
<summary>History</summary>
<br>

| Version | Changes          |
| ------- | ---------------- |
| 21.09.1 | Added in 21.09.1 |
</details>


The Start block is one of the primitive trigger blocks. It can be used to generate an event with a [Record](data-types.md#Record) containing the timestamp of when it was triggered.

!!!info 
When a new flow is created it comes with a Start block pre-created which in most cases will be the starting point for the flow.
!!!

+++ Output
| Port  | Symbol  | Description                                                            |
| ----- | ------- | ---------------------------------------------------------------------- |
| Event | `event` | Emits a `Record` containing the timestamp when the block was executed. |
+++