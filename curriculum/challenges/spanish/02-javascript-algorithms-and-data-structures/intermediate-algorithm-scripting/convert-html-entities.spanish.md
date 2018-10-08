---
id: a6b0bb188d873cb2c8729495
title: Convert HTML Entities
localeTitle: Convertir entidades HTML
isRequired: true
challengeType: 5
---

## Description
<section id='description'> 
Convierta los caracteres <code>&amp;</code> , <code>&lt;</code> , <code>&gt;</code> , <code>&quot;</code> (comillas dobles) y <code>&#39;</code> (apóstrofe), en una cadena a sus entidades HTML correspondientes. 
Recuerde usar <a href='http://forum.freecodecamp.org/t/how-to-get-help-when-you-are-stuck/19514' target='_blank'>Lectura-Búsqueda-Preguntar</a> si se atasca. Intente vincular el programa. Escribe tu propio código. 
</section>

## Instructions
<section id='instructions'> 

</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: &#39; <code>convertHTML(&quot;Dolce &amp; Gabbana&quot;)</code> debe devolver <code>Dolce &amp;​amp; Gabbana</code> .
    testString: 'assert.match(convertHTML("Dolce & Gabbana"), /Dolce &amp; Gabbana/, "<code>convertHTML("Dolce & Gabbana")</code> should return <code>Dolce &&#8203;amp; Gabbana</code>.");'
  - text: &#39; <code>convertHTML(&quot;Hamburgers &lt; Pizza &lt; Tacos&quot;)</code> debe devolver <code>Hamburgers &amp;​lt; Pizza &amp;​lt; Tacos</code> .
    testString: 'assert.match(convertHTML("Hamburgers < Pizza < Tacos"), /Hamburgers &lt; Pizza &lt; Tacos/, "<code>convertHTML("Hamburgers < Pizza < Tacos")</code> should return <code>Hamburgers &&#8203;lt; Pizza &&#8203;lt; Tacos</code>.");'
  - text: &#39; <code>convertHTML(&quot;Sixty &gt; twelve&quot;)</code> debe devolver <code>Sixty &amp;​gt; twelve</code> .
    testString: 'assert.match(convertHTML("Sixty > twelve"), /Sixty &gt; twelve/, "<code>convertHTML("Sixty > twelve")</code> should return <code>Sixty &&#8203;gt; twelve</code>.");'
  - text: &#39; <code>convertHTML(&#39;Stuff in &quot;quotation marks&quot;&#39;)</code> debería devolver <code>Stuff in &amp;​quot;quotation marks&amp;​quot;</code> .
    testString: 'assert.match(convertHTML("Stuff in "quotation marks""), /Stuff in &quot;quotation marks&quot;/, "<code>convertHTML(&apos;Stuff in "quotation marks"&apos;)</code> should return <code>Stuff in &&#8203;quot;quotation marks&&#8203;quot;</code>.");'
  - text: &#39; <code>convertHTML(&quot;Schindler&#39;s List&quot;)</code> debe devolver la <code>Schindler&amp;​apos;s List</code> .
    testString: 'assert.match(convertHTML("Schindler"s List"), /Schindler&apos;s List/, "<code>convertHTML("Schindler&apos;s List")</code> should return <code>Schindler&&#8203;apos;s List</code>.");'
  - text: &#39; <code>convertHTML(&quot;&lt;&gt;&quot;)</code> debe devolver <code>&amp;​lt;&amp;​gt;</code> .
    testString: 'assert.match(convertHTML("<>"), /&lt;&gt;/, "<code>convertHTML("<>")</code> should return <code>&&#8203;lt;&&#8203;gt;</code>.");'
  - text: <code>convertHTML(&quot;abc&quot;)</code> debe devolver <code>abc</code> .
    testString: 'assert.strictEqual(convertHTML("abc"), "abc", "<code>convertHTML("abc")</code> should return <code>abc</code>.");'

```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function convertHTML(str) {
  // &colon;&rpar;
  return str;
}

convertHTML("Dolce & Gabbana");
```

</div>



</section>

## Solution
<section id='solution'>


```js
var MAP = { '&': '&amp;',
            '<': '&lt;',
            '>': '&gt;',
            '"': '&quot;',
            "'": '&apos;'};

function convertHTML(str) {
  return str.replace(/[&<>"']/g, function(c) {
    return MAP[c];
  });
}
```

</section>