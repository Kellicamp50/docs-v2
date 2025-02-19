---
title: strings.toUpper() function
description: >
  `strings.toUpper()` converts a string to uppercase.
menu:
  flux_0_x_ref:
    name: strings.toUpper
    parent: strings
    identifier: strings/toUpper
weight: 101
---

<!------------------------------------------------------------------------------

IMPORTANT: This page was generated from comments in the Flux source code. Any
edits made directly to this page will be overwritten the next time the
documentation is generated. 

To make updates to this documentation, update the function comments above the
function definition in the Flux source code:

https://github.com/influxdata/flux/blob/master/stdlib/strings/strings.flux#L56-L56

Contributing to Flux: https://github.com/influxdata/flux#contributing
Fluxdoc syntax: https://github.com/influxdata/flux/blob/master/docs/fluxdoc.md

------------------------------------------------------------------------------->

`strings.toUpper()` converts a string to uppercase.

#### toUpper vs toTitle
The results of `toUpper()` and `toTitle()` are often the same, however the
difference is visible when using special characters:

```no_run
str = "ǳ"

strings.toUpper(v: str) // Returns Ǳ
strings.toTitle(v: str) // Returns ǲ
```

##### Function type signature

```js
(v: string) => string
```

{{% caption %}}For more information, see [Function type signatures](/flux/v0.x/function-type-signatures/).{{% /caption %}}

## Parameters

### v
({{< req >}})
String value to convert.




## Examples

### Convert all values of a column to upper case

```js
import "sampledata"
import "strings"

sampledata.string()
    |> map(fn: (r) => ({r with _value: strings.toUpper(v: r._value)}))

```

{{< expand-wrapper >}}
{{% expand "View example input and output" %}}

#### Input data

| _time                | *tag | _value      |
| -------------------- | ---- | ----------- |
| 2021-01-01T00:00:00Z | t1   | smpl_g9qczs |
| 2021-01-01T00:00:10Z | t1   | smpl_0mgv9n |
| 2021-01-01T00:00:20Z | t1   | smpl_phw664 |
| 2021-01-01T00:00:30Z | t1   | smpl_guvzy4 |
| 2021-01-01T00:00:40Z | t1   | smpl_5v3cce |
| 2021-01-01T00:00:50Z | t1   | smpl_s9fmgy |

| _time                | *tag | _value      |
| -------------------- | ---- | ----------- |
| 2021-01-01T00:00:00Z | t2   | smpl_b5eida |
| 2021-01-01T00:00:10Z | t2   | smpl_eu4oxp |
| 2021-01-01T00:00:20Z | t2   | smpl_5g7tz4 |
| 2021-01-01T00:00:30Z | t2   | smpl_sox1ut |
| 2021-01-01T00:00:40Z | t2   | smpl_wfm757 |
| 2021-01-01T00:00:50Z | t2   | smpl_dtn2bv |


#### Output data

| _time                | _value      | *tag |
| -------------------- | ----------- | ---- |
| 2021-01-01T00:00:00Z | SMPL_G9QCZS | t1   |
| 2021-01-01T00:00:10Z | SMPL_0MGV9N | t1   |
| 2021-01-01T00:00:20Z | SMPL_PHW664 | t1   |
| 2021-01-01T00:00:30Z | SMPL_GUVZY4 | t1   |
| 2021-01-01T00:00:40Z | SMPL_5V3CCE | t1   |
| 2021-01-01T00:00:50Z | SMPL_S9FMGY | t1   |

| _time                | _value      | *tag |
| -------------------- | ----------- | ---- |
| 2021-01-01T00:00:00Z | SMPL_B5EIDA | t2   |
| 2021-01-01T00:00:10Z | SMPL_EU4OXP | t2   |
| 2021-01-01T00:00:20Z | SMPL_5G7TZ4 | t2   |
| 2021-01-01T00:00:30Z | SMPL_SOX1UT | t2   |
| 2021-01-01T00:00:40Z | SMPL_WFM757 | t2   |
| 2021-01-01T00:00:50Z | SMPL_DTN2BV | t2   |

{{% /expand %}}
{{< /expand-wrapper >}}
