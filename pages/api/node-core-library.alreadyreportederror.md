---
layout: page
navigation_source: api_nav
improve_this_button: false
---
<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [@rushstack/node-core-library](./node-core-library.md) &gt; [AlreadyReportedError](./node-core-library.alreadyreportederror.md)

## AlreadyReportedError class

This exception can be thrown to indicate that an operation failed and an error message has already been reported appropriately. Thus, the catch handler does not have responsibility for reporting the error.

<b>Signature:</b>

```typescript
export declare class AlreadyReportedError extends Error 
```
<b>Extends:</b> Error

## Remarks

For example, suppose a tool writes interactive output to `console.log()`<!-- -->. When an exception is thrown, the `catch` handler will typically provide simplistic reporting such as this:

```ts
catch (error) {
  console.log("ERROR: " + error.message);
}

```
Suppose that the code performing the operation normally prints rich output to the console. It may be able to present an error message more nicely (for example, as part of a table, or structured log format). Throwing `AlreadyReportedError` provides a way to use exception handling to abort the operation, but instruct the `catch` handler not to print an error a second time:

```ts
catch (error) {
  if (error instanceof AlreadyReportedError) {
    return;
  }
  console.log("ERROR: " + error.message);
}

```

## Constructors

|  Constructor | Modifiers | Description |
|  --- | --- | --- |
|  [(constructor)()](./node-core-library.alreadyreportederror._constructor_.md) |  | Constructs a new instance of the <code>AlreadyReportedError</code> class |

## Methods

|  Method | Modifiers | Description |
|  --- | --- | --- |
|  [\[Symbol.hasInstance\](instance)](./node-core-library.alreadyreportederror._symbol.hasinstance_.md) | <code>static</code> |  |
