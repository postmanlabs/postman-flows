# Blocks

A block is a small actor/process that perform some predefine action. Flows comes in-built with some predefined blocks. A block starts executing when it has some data in all of it's input ports.

> This page is maintained as a source of truth for all the blocks that are available within Flows. Uses the ideas section of discussion to suggest any modifications in behavior to the existing blocks or any ideas for new blocks. 


## Stability
The block is an living standard and blocks go through a life-cycle as mentioned below

1. **Proposed** - This is proposed block that has not been implemented yet.

2. **Experimental** - This is a block that has been implement, but the API is not stable yet and may change in before becoming stable. 

3. **Standard** - This a block who API's have been frozen and not changes would be made.

4. **Deprecated** - This is a block which is no longer maintained or there is a newer better alternative block available as a replacement.

5. **Removed** - This is a block that once existed but is longer is available to
be used.

## List

Name |Stability| What can you do with it? | Added
-- | -- | -- | -- |
[Start](#Start) | Experimental | Starts the flow program | 21.09.1
[Send Request](#Send-Request) | Experimental | Executes the selected request | 21.09.1
[Terminal](#Terminal)| Experimental | Displays data that is incoming to the block | 21.09.1
[Assign Variables](#Assign-Variable)| Experimental | Assign strings to template variables
[Create Variable](#Create-Variable) | Experimental | Assign data from reference to template variables
[Delay](#Delay) | Experimental |Adds a delay | 21.09.1
[Test Summary](#Test-Summary) | Experimental | Fetches test summary of the request and displays it in terminal fashion
[Validate](#Validate)| Experimental | Checks if the query matches certain data or not | 21.09.1
[For Each](#For-Each) | Experimental | Iterate over list | 21.09.1
[Merge](#Merge) | Experimental |Takes 2 objects and merges them into a single object 
[List Pop](#List-Pop) | Experimental | Get element at index 0 of an array 
[Group By](#Group-By) | Experimental |Groups an array based on a specified key 
[Parse JSON](#Parse-JSON) | Experimental |Parses the incoming data to JSON | 21.09.1
[Concatenate](#Concatenate) | Experimental | Take 2 data pieces and put them in a single array list
[Condition] | Experimental | Checks for the given condition and passes data to either "Accept" or "Reject" port
[Check] | Experimental | Check for the given condition from 2 different inputs and pass data only if condition resolves to `True`


## Reference
### Start
Stage: Experimental

The *Start* block is one of the primitive trigger blocks. It can be used to generate an event with a [Record](data-types.md#Record) containing the timestamp of when it was triggered.
> When a new flow is created it comes with a Start block pre-created which in most cases will be the starting point for the flow.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Event (`event`) | `output` | Emits a `Record` containing the timestamp when the block was executed.|

---
### Send Request
Stage: Experimental

The `Send Request` block can be used to send one of the requests defined in a collection inside the current workspace.
This is block optionally accept a Record in its variable port and uses it to generate data-variable to satisfy the variables used within the selected Request.


| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Variables (`variables`) | `input` (optional) | Accepts a `Record` containing key value pairs which will be converted to the variables. Nested Records will be [flattened](https://www.npmjs.com/package/flat).|
| Response (`response`) | `output` | Emits a `Record` of the response received for this request |
| Test (`test`) | `output` | Emits a `List` of all the tests that were executed for this request. No list will be emitted if the request does not contain any tests.|

#### Response Record Schema
```yaml
response: Record
  body: string
  headers: Map
    {key}: string
  http: Record
    statusCode: number
    statusMessage: string
    version: string
    responseTime: number
```
#### Test List Schema
```yaml
test: List
  - {element}: Record
      index: number
      name: string
      passed: bool
      skipped: bool
      [error]: Record (Optional)
        actual: string
        expected: string
        message: string
```

---
### Terminal
Stage: Experimental

The *Terminal* block can be used to print the data emitted by any port to the terminal panel. This is similar to using `console.log` in javascript or `System.out.println()` in Java. It takes data from any port, formats it in yaml and prints it in the screen or standard-output. 

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts any type of data |

---
### Assign Variable
Stage: Experimental
> Warning: This block has been marked to removed in the future versions. Working with variables will be restricted to the Send Request block.

The *assign variable* can be used to take any type of input data and convert it to a `Map` containing strings as values, that can be used as a data-variable. The assign variable block is not capable of defining constant string values. If string values are needed the [Create Variable](#Create-Variable) block can be used in conjunction with the [Merge](#Merge) block. 

> Note: Nested records are not supported, the values of the records can only be strings or values that can be casted to a string.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts any type of data |
| Variables (`variables`) | `output` | Emits a `Map<string, string>` which can be used to generate variables in a *Send Request* block |

---
### Create Variable
Stage: Experimental

> Warning: This block has been marked to removed in the future versions. Working with variables will be restricted to the Send Request block.

The *create variable* block can be used define a `Map` containing constant string values. 

> Note: Nested records are not supported, the values of the records can only be strings or values that can be casted to a string.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Trigger (`trigger`) | `input` | Accepts any type of data to trigger the creation |
| Variables (`variables`) | `output` | Emits a `Map<string, string>` which can be used to generate variables in a *Send Request* block |

---
### Delay
Stage: Experimental

The *delay* block can be used to hold a data packet for a fixed duration of time before emitting it out. One of the use-case for this block is to add a delay between two Send Request blocks. It can be considered equivalent to `setTimeout` in Javascript.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts any type of data |
| Data (`data`) | `output` | Emits any type of data it has accepted|

---
### Test Summary
Stage: Experimental

The *test summary* block is special output block like terminal which can accept the data emitted from the test port of *Send Request* block. 
The summary of all the assertions can be seen in the *Test Summary* panel.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Test (`test`) | `input` | Accepts a [Test List](#Test-List-Schema) |

---
### Validate
Stage: Experimental

> Warning: This block has been marked to removed in the future versions. This will be replace by a more versatile Check block.

The *Validate* block is a conditional flow control block that routes a data packet to either the `true` port or `false` port based on condition. This block uses some information present within the data itself to perform the validation check.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`)  | `input`  | Accepts any type of data. |
| True (`true`) | `output` | Emits the accepted data if the validation passes. |
| False (`false`) | `output` | Emits the accepted data if the validation fails. |

---
### For Each
Stage: Experimental

The *For Each* block is an iterator control flow block that can be used to loop over a `List`. The block emits each individual element within the list as a separate data packet. 

> Note: The signal port behaviour of the blocks connected after the For Each block is different. The for each block is special because it generates a stream of data. Each data packet generated from a single list are bracketed under a single stream. So the signal ports of every block down stream only turns to low when the entire stream has been processed. 

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts any type of data which contains a List |
| Data (`data`) | `output<stream>` | Emits a stream of individual element of the list|

---
### Merge
Stage: Experimental

The *Merge* block can be used to recursively merge two `Records` into a single `Record`.
> Note: If both source and target contain fields with same keys, then target value will be overridden by the source.


| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Target (`target`) | `input` | Accepts data containing a Record |
| Source (`source`) | `input` | Accepts data containing another Record |
| Data (`data`) | `output` | Emits a Record with fields merged |

> Tip: You may be tempted to use merge block to synchronize different data source to perform flow control. This is not advisable, instead use Signal Port to perform flow control.

---
### List Pop
Stage: Experimental

The *List Pop* block can be used to get the last element of a List.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts data containing a List |
| Last (`last`) | `output` | Emits the last element of the List |
| Rest (`rest`) | `output` | Emits the list without the last element |

---
### Group By
Stage: Experimental

The *Group By* block can be used generate another list by grouping together Records presents in a List based on a value present in one of the selected fields.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts data containing a List |
| Group (`group`) | `output` | Emits the new list with different groups |

---

### Concatenate
Stage: Experimental

> Warning: This block has been marked to removed in the future versions. This will be replace by a more versatile stream processing blocks.

The *Concatenate* block can be used to append a element to a List to create a 
new List.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| List (`list`) | `input` | Accepts a List |
| Data (`data`) | `input` | Accepts data to be appended to the List |
| Group (`group`) | `output` | Emits the new list with element added |

---

### Parse JSON
Stage: Experimental

> Warning: This block has been marked to removed in the future versions. This will be replace by a more generic parsing block.

The *Parse JSON* block can be used to parse any JSON string and create a flow data packet to be used in the program. 

> Note: The Send Request block automatically performs JSON parsing on bodies that have their content-type header set to JSON. This block will only be needed in the off-chance that automatic parsing does not take place in the Send Request block.


| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts data containing a json string |
| JSON (`json`) | `output` | Emits a parsed data packet of JSON string |

---

### Condition
The *Condition* block lets you write expressions with the new [Expression input](https://github.com/postmanlabs/postman-flows/discussions/124). If the condition resolves to `True` it passes the data through the "Accept" port, and if the expression resolves to `False` it passes the data through "Reject" port

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Data (`data`) | `input` | Accepts data on which decision is to be made |
| Accept (`Accept`) | `output` | Passes data received if the condition resolves to `True` |
| Reject (`Reject`) | `output` | Passes data received if the condition resolves to `False` |

---

### Check
The *Check* block accepts input from 2 sources and lets you write expressions with the new [Expression input](https://github.com/postmanlabs/postman-flows/discussions/124). If the condition resolves to `True` it passes the data through otherwise burns the data away.

| Port (`symbol`) | Type | Description |
| --- | --- | --- |
| Primary (`Primary`) | `input` | Data which needs to pass through if condition resolves to `True` |
| Secondary (`Secondary`) | `input` | Other source of data which does not pass through |
| Primary (`Primary`) | `output` | Passes data received from `Primary` input port if the condition resolves to `True`|

---
