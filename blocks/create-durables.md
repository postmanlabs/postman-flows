# Create Durables

[!badge text="Experimental" variant="primary"]

==- :icon-history: History

| Version | Changes           |
| ------- | ----------------- |
| 21.12.2 | Added in v21.12.2 |

===

The **Create Durables** allows bool, number, string and timestamp values to be made durable.
Durables or durable data is the data that can persists across multiple connected blocks.

+++ Input
| Port | Symbol | Description                                               |
| ---- | ------ | --------------------------------------------------------- |
| Data | `data` | Accepts the data whose values can be assigned to durables |
+++ Output
| Port | Symbol | Description                                                                  |
| ---- | ------ | ---------------------------------------------------------------------------- |
| Data | `data` | Provides newly created durables and the data received from `Data` input port |
+++