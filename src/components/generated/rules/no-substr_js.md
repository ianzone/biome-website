**Since**: `vnext`
:::note
- This rule has an **unsafe** fix.
:::

:::caution
This rule is part of the [nursery](/linter/rules/#nursery) group.
:::

Sources: 
- Same as: <a href="https://github.com/sindresorhus/eslint-plugin-unicorn/blob/main/docs/rules/prefer-string-slice.md" target="_blank"><code>unicorn/prefer-string-slice</code></a>

Enforce the use of `String.slice()` over `String.substr()` and `String.substring()`.

`String.slice()` is preferred over `String.substr()` and `String.substring()` because it is a more popular option with clearer behavior,
and it has a consistent counterpart in arrays.

Note that `String.substr`, `String.substring` and `String.slice` are not identical when arguments are passed.
For detailed differences, refer to the MDN documentation:

- [The difference between substring() and substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring#the_difference_between_substring_and_substr)
- [Differences between substring() and slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring#differences_between_substring_and_slice)

## Examples

### Invalid

```js
foo.substr();
```

<pre class="language-text"><code class="language-text">code-block.js:1:5 <a href="https://biomejs.dev/linter/rules/no-substr">lint/nursery/noSubstr</a> <span style="color: #000; background-color: #ddd;"> FIXABLE </span> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

<strong><span style="color: Orange;">  </span></strong><strong><span style="color: Orange;">⚠</span></strong> <span style="color: Orange;">Avoid using substr and consider using slice instead.</span>
  
<strong><span style="color: Tomato;">  </span></strong><strong><span style="color: Tomato;">&gt;</span></strong> <strong>1 │ </strong>foo.substr();
   <strong>   │ </strong>    <strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong>
    <strong>2 │ </strong>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;"><strong>slice</strong></span><span style="color: lightgreen;"> is more commonly used and has a less surprising behavior.</span>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;">See </span><span style="color: lightgreen;"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring#the_difference_between_substring_and_substr">MDN web docs</a></span><span style="color: lightgreen;"> for more details.</span>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;">Unsafe fix</span><span style="color: lightgreen;">: </span><span style="color: lightgreen;">Use </span><span style="color: lightgreen;"><strong>.slice()</strong></span><span style="color: lightgreen;"> instead.</span>
  
    <strong>1</strong>  <strong> │ </strong><span style="color: Tomato;">-</span> <span style="color: Tomato;">f</span><span style="color: Tomato;">o</span><span style="color: Tomato;">o</span><span style="color: Tomato;">.</span><span style="color: Tomato;"><strong>s</strong></span><span style="color: Tomato;"><strong>u</strong></span><span style="color: Tomato;"><strong>b</strong></span><span style="color: Tomato;"><strong>s</strong></span><span style="color: Tomato;"><strong>t</strong></span><span style="color: Tomato;"><strong>r</strong></span><span style="color: Tomato;">(</span><span style="color: Tomato;">)</span><span style="color: Tomato;">;</span>
      <strong>1</strong><strong> │ </strong><span style="color: MediumSeaGreen;">+</span> <span style="color: MediumSeaGreen;">f</span><span style="color: MediumSeaGreen;">o</span><span style="color: MediumSeaGreen;">o</span><span style="color: MediumSeaGreen;">.</span><span style="color: MediumSeaGreen;"><strong>s</strong></span><span style="color: MediumSeaGreen;"><strong>l</strong></span><span style="color: MediumSeaGreen;"><strong>i</strong></span><span style="color: MediumSeaGreen;"><strong>c</strong></span><span style="color: MediumSeaGreen;"><strong>e</strong></span><span style="color: MediumSeaGreen;">(</span><span style="color: MediumSeaGreen;">)</span><span style="color: MediumSeaGreen;">;</span>
    <strong>2</strong> <strong>2</strong><strong> │ </strong>  
  
</code></pre>

```js
foo.substring();
```

<pre class="language-text"><code class="language-text">code-block.js:1:5 <a href="https://biomejs.dev/linter/rules/no-substr">lint/nursery/noSubstr</a> <span style="color: #000; background-color: #ddd;"> FIXABLE </span> ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

<strong><span style="color: Orange;">  </span></strong><strong><span style="color: Orange;">⚠</span></strong> <span style="color: Orange;">Avoid using substring and consider using slice instead.</span>
  
<strong><span style="color: Tomato;">  </span></strong><strong><span style="color: Tomato;">&gt;</span></strong> <strong>1 │ </strong>foo.substring();
   <strong>   │ </strong>    <strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong><strong><span style="color: Tomato;">^</span></strong>
    <strong>2 │ </strong>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;"><strong>slice</strong></span><span style="color: lightgreen;"> is more commonly used and has a less surprising behavior.</span>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;">See </span><span style="color: lightgreen;"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring#the_difference_between_substring_and_substr">MDN web docs</a></span><span style="color: lightgreen;"> for more details.</span>
  
<strong><span style="color: lightgreen;">  </span></strong><strong><span style="color: lightgreen;">ℹ</span></strong> <span style="color: lightgreen;">Unsafe fix</span><span style="color: lightgreen;">: </span><span style="color: lightgreen;">Use </span><span style="color: lightgreen;"><strong>.slice()</strong></span><span style="color: lightgreen;"> instead.</span>
  
    <strong>1</strong>  <strong> │ </strong><span style="color: Tomato;">-</span> <span style="color: Tomato;">f</span><span style="color: Tomato;">o</span><span style="color: Tomato;">o</span><span style="color: Tomato;">.</span><span style="color: Tomato;"><strong>s</strong></span><span style="color: Tomato;"><strong>u</strong></span><span style="color: Tomato;"><strong>b</strong></span><span style="color: Tomato;"><strong>s</strong></span><span style="color: Tomato;"><strong>t</strong></span><span style="color: Tomato;"><strong>r</strong></span><span style="color: Tomato;"><strong>i</strong></span><span style="color: Tomato;"><strong>n</strong></span><span style="color: Tomato;"><strong>g</strong></span><span style="color: Tomato;">(</span><span style="color: Tomato;">)</span><span style="color: Tomato;">;</span>
      <strong>1</strong><strong> │ </strong><span style="color: MediumSeaGreen;">+</span> <span style="color: MediumSeaGreen;">f</span><span style="color: MediumSeaGreen;">o</span><span style="color: MediumSeaGreen;">o</span><span style="color: MediumSeaGreen;">.</span><span style="color: MediumSeaGreen;"><strong>s</strong></span><span style="color: MediumSeaGreen;"><strong>l</strong></span><span style="color: MediumSeaGreen;"><strong>i</strong></span><span style="color: MediumSeaGreen;"><strong>c</strong></span><span style="color: MediumSeaGreen;"><strong>e</strong></span><span style="color: MediumSeaGreen;">(</span><span style="color: MediumSeaGreen;">)</span><span style="color: MediumSeaGreen;">;</span>
    <strong>2</strong> <strong>2</strong><strong> │ </strong>  
  
</code></pre>

### Valid

```js
foo.slice(beginIndex, endIndex);
```

## Related links

- [Disable a rule](/linter/#disable-a-lint-rule)
- [Configure the rule fix](/linter#configure-the-rule-fix)
- [Rule options](/linter/#rule-options)