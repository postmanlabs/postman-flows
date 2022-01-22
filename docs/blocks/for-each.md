# For Each
[!badge text="Experimental" variant="primary"]

<details>
<summary>History</summary>
<br>

| Version | Changes           |
| ------- | ----------------- |
| 21.09.1 | Added in v21.09.1 |
</details>

The *For Each* block is an iterator control flow block that can be used to loop over a `List`. The block emits each individual element within the list as a separate data packet. 

!!!info 
The signal port behaviour of the blocks connected after the For Each block is different. The for each block is special because it generates a stream of data. Each data packet generated from a single list are bracketed under a single stream. So the signal ports of every block down stream only turns to low when the entire stream has been processed.
!!! 

+++ Input
| Port | Symbol | Description                                    |
| ---- | ------ | ---------------------------------------------- |
| Data | `data` | Accepts any type of data which contains a List |
+++ Output
| Port | Symbol         | Description                                      |
| ---- | -------------- | ------------------------------------------------ |
| Data | `data<stream>` | Emits a stream of individual element of the list |
+++



