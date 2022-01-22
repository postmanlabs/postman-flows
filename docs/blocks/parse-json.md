# Parse JSON
Stage: [!badge text="Removed" variant="danger"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 22.01.1 | Removed           |
| 21.09.1 | Added in v21.09.1 |
</details>

!!!danger Removed
Use **Send Request** block *Parse body* configuration to force parse response bodies to JSON.
!!!

The *Parse JSON* block can be used to parse any JSON string and create a flow data packet to be used in the program. 

!!!info
The Send Request block automatically performs JSON parsing on bodies that have their content-type header set to JSON. This block will only be needed in the off-chance that automatic parsing does not take place in the Send Request block.
!!!

+++ Input
| Port | Symbol | Description                           |
| ---- | ------ | ------------------------------------- |
| Data | `data` | Accepts data containing a json string |
+++ Output
| Port | Symbol | Description                               |
| ---- | ------ | ----------------------------------------- |
| JSON | `json` | Emits a parsed data packet of JSON string |
+++

