# Concatenate

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.09.1 | Added in v21.09.1 |

===

!!!warning
This block will be removed in the future versions and replace by a more versatile stream processing blocks.
Please use with caution!
!!!

The **Concatenate** block can be used to append a element to a List to create a
new List.

+++ Input
| Port | Symbol | Description                             |
| ---- | ------ | --------------------------------------- |
| List | `list` | Accepts a List                          |
| Data | `data` | Accepts data to be appended to the List |
+++ Output
| Port  | Symbol  | Description                           |
| ----- | ------- | ------------------------------------- |
| Group | `group` | Emits the new list with element added |
+++
