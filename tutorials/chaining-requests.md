---
order: 97
---
# Level 2 - Chaining requests

!!!warning
This tutorial is under-construction
!!!

## Simple

### 1. Add a `Send Request` block from the block list to the canvas and select the first request

### 2 Add another `Send Request` block from the block list to the canvas and select the second request

### 3. Pipe the data from the `response` output of the first block to the `variables`input of the second block

### 4. Use the variables in the request using the request builder.

### 5. Start the Flow


### Conditional

There might be situations where we want to conditionally send the second request.

### 1. Add an `Example` to the first request. (Important)

### 2. Add a `Condition` block in-between the first and second request.

### 3. Add a `truthy` expression to conditionally pipe the data from first request to second

### 4. Start the Flow