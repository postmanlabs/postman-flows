# Expressions & Operators

Expression and operators are the means why which you can operate over all kinds of
data within Flows. There are various kinds of operators that can be combined with
data literals and data references to transform or create new data.

## Operators

These are operators that flows currently supports

### Comparison Operators

| Operator                              | Description                                                                   | Left                                                   | Right                                                  | Result |
| ------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------ |
| [!badge text="==" variant="info"]     | Evaluates to `true` if operands are same                                      | `number` </br> `string` </br> `bool` </br> `timestamp` | `number` </br> `string` </br> `bool` </br> `timestamp` | `bool` |
| [!badge text="!=" variant="info"]     | Evaluates to `true` if operands are not same                                  | `number` </br> `string` </br> `bool` </br> `timestamp` | `number` </br> `string` </br> `bool` </br> `timestamp` | `bool` |
| [!badge text="in" variant="info"]     | Evaluates to `true` if string on left is substring of the right               | `string`                                               | `string`                                               | `bool` |
| [!badge text="in" variant="info"]     | Evaluates to `true` if the specified field is present in the Record           | `string`                                               | `record`                                               | `bool` |
| [!badge text="!in" variant="info"]    | Evaluates to `true` if string on left is not a substring of the right         | `string`                                               | `string`                                               | `bool` |
| [!badge text="!in" variant="info"]    | Evaluates to `true` if the specified field is not present in the Record       | `string`                                               | `record`                                               | `bool` |
| [!badge text="match" variant="info"]  | Evaluates to `true` if the string matches the regular expression              | `string`                                               | `regex`                                                | `bool` |
| [!badge text="!match" variant="info"] | Evaluates to `true` if the string does not match the regular expression       | `string`                                               | `regex`                                                | `bool` |
| [!badge text="is" variant="info"]     | Evaluates to `true` if the expression is of the type                          | `any`                                                  | `datatype`                                             | `bool` |
| [!badge text="!is" variant="info"]    | Evaluates to `true` if the expression if not of the type                      | `any`                                                  | `datatype`                                             | `bool` |
| [!badge text ="<" variant="info"]     | Evaluates to `true` if left operand is less than right operand                | `number` </br> `timestamp`                             | `number` </br> `timestamp`                             | `bool` |
| [!badge text ="<=" variant="info"]    | Evaluates to `true` if left operand is less than or equal to right operand    | `number` </br> `timestamp`                             | `number` </br> `timestamp`                             | `bool` |
| [!badge text =">" variant="info"]     | Evaluates to `true` if left operand is greater than right operand             | `number` </br> `timestamp`                             | `number` </br> `timestamp`                             | `bool` |
| [!badge text =">=" variant="info"]    | Evaluates to `true` if left operand is greater than or equal to right operand | `number` </br> `timestamp`                             | `number` </br> `timestamp`                             | `bool` |

### Logical Operators

| Operator                           | Description                                                 | Left   | Right  | Result |
| ---------------------------------- | ----------------------------------------------------------- | ------ | ------ | ------ |
| [!badge text="AND" variant="info"] | Evaluates to `true` when both operands evaluate to `true`   | `bool` | `bool` | `bool` |
| [!badge text="OR" variant="info"]  | Evaluates to `true` when either operands evaluate to `true` | `bool` | `bool` | `bool` |
| [!badge text="!" variant="info"]   | Evaluates to `true` when operand is `false` and vice-versa  |        | `bool` | `bool` |


### Unary Operators

| Operator                                | Description                                | Operand                                 | Result   |
| --------------------------------------- | ------------------------------------------ | --------------------------------------- | -------- |
| [!badge text="to_json" variant="info" ] | Serialized a structure to a JSON String    | `record`/`list`/`map`/`tuple`           | `string` |
| [!badge text="length" variant="info" ]  | Evaluates to the length of the data        | `string`/ `record`/`list`/`map`/`tuple` | `number` |
| [!badge text="size" variant="info" ]    | Evaluates to the size in bytes of the data | `string`/ `record`/`list`/`map`/`tuple` | `number` |

### Query Operators

| Operator                            | Description                                                                   | Left   | Right  | Result |
| ----------------------------------- | ----------------------------------------------------------------------------- | ------ | ------ | ------ |
| [!badge text="find" variant="info"] | Returns an new list where the right expression evaluates to true for the item | `list` | `bool` | `list` |

### Proposals

!!!warning
These operators are in proposal stage and may/may-not be implemented. Please help us make
better decision by showing you use-cases in [Discussions](https://github.com/postmanlabs/postman-flows/discussions).
!!!

| Operator | Description                                                                                                   |
| -------- | ------------------------------------------------------------------------------------------------------------- |
| sort     | Returns a sorted list                                                                                         |
| groupby  | Returns a record which contains fields that group a particular list                                           |
| +        | Sum and Concatenation operators. Can be used to add numbers, concatenate string and list and merge records    |
| -        | Subtract and Difference operator. Can be used to subtract number, strip string and list, different on records |
| *        | Multiplication of numbers                                                                                     |
| /        | Division of numbers                                                                                           |
| %        | Remainder operator                                                                                            |
| ^        | Exponent operator                                                                                             |
