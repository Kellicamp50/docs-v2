---
title: strings.splitAfter() function
description: >
  `strings.splitAfter()` splits a string after a specified separator and returns an array of substrings.
  Split substrings include the separator, `t`.
menu:
  flux_0_x_ref:
    name: strings.splitAfter
    parent: strings
    identifier: strings/splitAfter
weight: 101
---

<!------------------------------------------------------------------------------

IMPORTANT: This page was generated from comments in the Flux source code. Any
edits made directly to this page will be overwritten the next time the
documentation is generated. 

To make updates to this documentation, update the function comments above the
function definition in the Flux source code:

https://github.com/influxdata/flux/blob/master/stdlib/strings/strings.flux#L711-L711

Contributing to Flux: https://github.com/influxdata/flux#contributing
Fluxdoc syntax: https://github.com/influxdata/flux/blob/master/docs/fluxdoc.md

------------------------------------------------------------------------------->

`strings.splitAfter()` splits a string after a specified separator and returns an array of substrings.
Split substrings include the separator, `t`.



##### Function type signature

```js
(t: string, v: string) => [string]
```

{{% caption %}}For more information, see [Function type signatures](/flux/v0.x/function-type-signatures/).{{% /caption %}}

## Parameters

### v
({{< req >}})
String value to split.



### t
({{< req >}})
String value that acts as the separator.




## Examples

### Split a string into an array of substrings

```js
import "strings"

strings.splitAfter(v: "foo, bar, baz, quz", t: ", ")// Returns ["foo, ", "bar, ", "baz, ", "quz"]


```

