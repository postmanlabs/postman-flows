# List Pop

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.10.4 | Added in v21.10.4 |

===

The **List Pop** block can be used to get the last element of a List.

!!!warning
This block will be removed in the future versions and proper operator will be added in expressions.
Please use with caution!
!!!

+++ Input
| Port | Symbol | Description                    |
| ---- | ------ | ------------------------------ |
| Data | `data` | Accepts data containing a List |
+++ Output
| Port | Symbol | Description                             |
| ---- | ------ | --------------------------------------- |
| Last | `last` | Emits the last element of the List      |
| Rest | `rest` | Emits the list without the last element |
+++


