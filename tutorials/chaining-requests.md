---
order: 97
---
# Level 2 - Chaining requests

Chaining request is the ability of send one request after another either in serial or parallel.

## Simple
If you have a bunch of simple requests that have no dependency on each other but
they have to be executed in a particular order, it's as simple as

### 1. Add the [Send Request](./../blocks/send-request.md) blocks
Click on the `+ Block` button on the toolbar and select the [Send Request](./../blocks/send-request.md) from the list to add to your canvas, then select the request. Repeat this
setup until all the requests are added to the canvas.

![](../static/chaining/add-requests.gif)

### 2. Connect the signals
Click on the grey dot (signal output) of the source block and connect it to 
signal input of the target block in the order you want the requests to execute.
![](../static/chaining/connect-signals.gif)
Here, two `Create a post` are executed in parallel. When both of the request has completed,
the `Get all posts` endpoint is called, and then finally `Delete all posts is called`.

!!!success Important
1. When a signal connection is made the input become disabled to show that it will get enabled
   after the previous blocks get enabled.
2. The signal connection depict exactly the order in which the blocks will be executed.
3. When using signal no data is passed from one block to another.
4. Two or more connections can be made to an input. The block will execute only when all signals
   have got enabled.
!!!

### 3. Start the Flow
Start the flow see them run in the order they are configured!
![](../static/chaining/run-with-signals.gif)

## Passing Data

### 1 Add a [Send Request](./../blocks/send-request.md) block
Click on the `+ Block` button on the toolbar and select the [Send Request](./../blocks/send-request.md) from the list to add to your canvas, then select the request.
![](../static/chaining/add-first-request.gif)

### 2 Add another `Send Request` block 
Add another `Send request` block and add the request you want to send the data to here 
![](../static/chaining/add-second-request.gif)

### 3. Pipe the data
Now we need to tell the flow where the data should _flow_. To do that, COnnect the `response` output of the first block to the `variables`input of the second block.
![](../static/chaining/pipe-data.gif)

### 4. Use the variables
To tell the request what to use from the input received, you use variables. Create a template variable in the request where you want the data to fit in. 
Then in the flow, click on `Add Variables`, select the name of the variable and assign it data comming in from the input port `Variables`.
![](../static/chaining/use-variables.gif)

### 5. Start the Flow
Start the flow and the data will _flow_ through!
![](../static/chaining/start-flow.gif)


!!!warning
The rest of this tutorial is under-construction
!!!

## Conditional

There might be situations where we want to conditionally send the second request.

### 1. Add an `Example` to the first request. (Important)

### 2. Add a `Condition` block in-between the first and second request.

### 3. Add a `truthy` expression to conditionally pipe the data from first request to second

### 4. Start the Flow