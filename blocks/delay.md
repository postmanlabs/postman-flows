# Delay

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.09.1 | Added in v21.09.1 |

===

The **delay** block can be used to hold a data packet for a fixed duration of time before emitting it out. One of the use-case for this block is to add a delay between two Send Request blocks. It can be considered equivalent to `setTimeout` in Javascript.

+++ Input
| Port | Symbol | Description              |
| ---- | ------ | ------------------------ |
| Data | `data` | Accepts any type of data |
+++ Output
| Port | Symbol | Description                            |
| ---- | ------ | -------------------------------------- |
| Data | `data` | Emits any type of data it has accepted |
+++
