## Functions

<dl>
<dt><a href="#encodeName">encodeName(name)</a> ⇒ <code>string.&lt;uint64&gt;</code></dt>
<dd><p>Encode a name (a base32 string) to a number.</p>
<p>  For performance reasons, the blockchain uses the numerical encoding of strings
  for very common types like account names.</p>
</dd>
<dt><a href="#decodeName">decodeName(value)</a> ⇒ <code>string</code></dt>
<dd></dd>
<dt><a href="#UDecimalString">UDecimalString()</a> ⇒ <code>string</code></dt>
<dd><p>Normalize and validate decimal string (potentially large values).  Should
  avoid internationalization issues if possible but will be safe and
  throw an error for an invalid number.</p>
<p>  Normalization removes extra zeros or decimal.</p>
</dd>
<dt><a href="#UDecimalPad">UDecimalPad(value, precision)</a> ⇒ <code>string</code></dt>
<dd><p>Ensure a fixed number of decimal places.  Safe for large numbers.</p>
</dd>
<dt><a href="#UDecimalImply">UDecimalImply()</a></dt>
<dd><p>Ensures proper trailing zeros then removes decimal place.</p>
</dd>
<dt><a href="#UDecimalUnimply">UDecimalUnimply(value, precision)</a> ⇒ <code>number</code></dt>
<dd><p>Put the decimal place back in its position and return the normalized number
  string (with any unnecessary zeros or an unnecessary decimal removed).</p>
</dd>
</dl>

<a name="encodeName"></a>

## encodeName(name) ⇒ <code>string.&lt;uint64&gt;</code>
Encode a name (a base32 string) to a number.

  For performance reasons, the blockchain uses the numerical encoding of strings
  for very common types like account names.

**Kind**: global function  
**Returns**: <code>string.&lt;uint64&gt;</code> - - compressed string (from name arg).  A string is
    always used because a number could exceed JavaScript's 52 bit limit.  
**See**: types.hpp string_to_name  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | A string to encode, up to 12 characters long. |

<a name="decodeName"></a>

## decodeName(value) ⇒ <code>string</code>
**Kind**: global function  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>Long</code> \| <code>String</code> \| <code>number</code> | uint64 |

<a name="UDecimalString"></a>

## UDecimalString() ⇒ <code>string</code>
Normalize and validate decimal string (potentially large values).  Should
  avoid internationalization issues if possible but will be safe and
  throw an error for an invalid number.

  Normalization removes extra zeros or decimal.

**Kind**: global function  
**Returns**: <code>string</code> - value  
<a name="UDecimalPad"></a>

## UDecimalPad(value, precision) ⇒ <code>string</code>
Ensure a fixed number of decimal places.  Safe for large numbers.

**Kind**: global function  
**Returns**: <code>string</code> - decimal part is added and zero padded to match precision  
**See**: ./format.test.js  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>number</code> \| <code>string</code> \| <code>object.toString</code> |  |
| precision | <code>number</code> | number of decimal places |

**Example**  
```js
UDecimalString(10, 3) === '10.300'

  
```
<a name="UDecimalImply"></a>

## UDecimalImply()
Ensures proper trailing zeros then removes decimal place.

**Kind**: global function  
<a name="UDecimalUnimply"></a>

## UDecimalUnimply(value, precision) ⇒ <code>number</code>
Put the decimal place back in its position and return the normalized number
  string (with any unnecessary zeros or an unnecessary decimal removed).

**Kind**: global function  
**Returns**: <code>number</code> - 1.0000  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>string</code> \| <code>number</code> \| <code>value.toString</code> | 10000 |
| precision | <code>number</code> | 4 |

