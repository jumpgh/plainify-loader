# plainify-loader

  [![npm version](https://badge.fury.io/js/plainify-loader.svg)](https://badge.fury.io/js/plainify-loader)
  [![Build Status](https://travis-ci.org/demiazz/plainify-loader.svg?branch=master)](https://travis-ci.org/demiazz/plainify-loader)

Convert JSON to plain object.

<a href="https://evilmartians.com/?utm_source=postcss">
  <img src="https://evilmartians.com/badges/sponsored-by-evil-martians.svg"
       alt="Sponsored by Evil Martians" width="236" height="54">
</a>

## Why?

Loader developed for usage with `react-intl` which can use only
plain objects as messages object.

But I like structure used in `counterpart.js` or `Rails I18n`, where locales
represents as nested object, but ids used by library for traversing over
the locales.

## Example

### in

```json
{
  "key": "value",
  "nested": {
    "other_key": "other_value"
  }
}
```

### out

```json
{
  "key": "value",
  "nested.other_key": "other_value"
}
```

## Warning

The loader provides support only for values represented as strings or objects
with strings values because developed for the particular usage.

## Installation

```sh
npm install plainify-loader
```

## Usage

```js
import json from 'json!plainify!./file.json';
// => returns file.json content as JSON parsed and plainified object
```

or you can use it with `yaml-loader`

```js
import json from 'json!plainify!yaml!./file.yml';
// => returns file.yml content as YAML parsed and plainified object
```
