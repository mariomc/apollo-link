# Batch Link

## Purpose
An Apollo Link to allow batching of multiple operations into a single request. For example, the `apollo-link-batch-http` uses this link to batch operations into a single http request.

## Usage
```js
import BatchLink from "apollo-link-batch";

const link = new BatchLink({
  batchHandler: (operations: Operation[], forward: NextLink) => Observable<FetchResult[]> | null
});
```

## Options
Batch Link takes an object with three options on it to customize the behavoir of the link. The only required option is the batchHandler function

|name|value|default|required|
|---|---|---|---|
|batchInterval|number|10|false|
|batchMax|number|0|false|
|batchHandler|(operations: Operation[], forward: NextLink) => Observable<FetchResult[]> | null|NA|true|

## Context
The Batch Link does not use the context for anything