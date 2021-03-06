<p align="center">
  <img src="https://github.com/etienne-dldc/literal-parser/blob/master/design/logo.svg" width="700" alt="literal-parser logo">
</p>

# 🔎 literal-parser

> A small library to parse and serialize JavaScript array/object literal.

This is like a `JSON.parse` / `JSON.serialize` but for JavaScript object instead of JSON objects.

## Gist

```js
import Parser from "literal-parser";

Parser.parse('{ some: ["object", { literal: true }] }');
// return an object { some: ["object", { literal: true }] }
```

## Supported features

Take a look at the tests see what is supported.

## API

### `Parser.parse(str)`

Parse the string, expect the string to contain only one expression and throw otherwise.

Return the parsed object.

### `Parser.parseOne(str)`

Parse one expression then stop.

Returns a object with `{ value, length }` where `value` is the parsed expression and `length` is the number of character parsed.

```js
Parser.parseOne('{ props: true }} something="else" />');
// { value: { props: true }, length: 15 }
```

### `Serializer.serialize(obj)`

Print an object.
