# Merge

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.10.2 | Added in v21.10.2 |

===

The **Merge** block can be used to recursively merge two `Records` into a single `Record`.

!!!info
When both source and target contain records fields with same name, then target value will be overridden by the source.
!!!

+++ Input
| Port   | Symbol   | Description                            |
| ------ | -------- | -------------------------------------- |
| Target | `target` | Accepts data containing a Record       |
| Source | `source` | Accepts data containing another Record |
+++ Output
| Port | Symbol | Description                       |
| ---- | ------ | --------------------------------- |
| Data | `data` | Emits a Record with fields merged |
+++

!!!  Tip
You may be tempted to use merge block to synchronize different data source to perform flow control. This is not advisable, instead use Signal Port to perform flow control.
!!!
