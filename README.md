# ElGen
Generates multiple HTML elements using only plain Javascript.

The ElGen.js is designed for generating HTML elements with a template and data provided.

Similar to Vue.js, this code allows data to be inserted in HTML code. So, you only have to make a template and it'll create the elements for you. The only downside to it is **it doesn't have realtime linking to the data**. Once the data changes, you will have to regenerate the HTML elements.

### Syntax

```Javascript
ElGen.run(template, data, config);
```
---

An example of a `template` is
```Javascript
var template = {
  node: "div", //the tag name of the element
  attr: { "attribute_name" : "attribute_value" }, //an object containing attributes (optional)
  html: "innerHTML_content", //the innerHTML of the element (optional)
  children: [{ //an array of the children of the element (optional)
    node: "node_name",
    attr: { "attribute_name" : "attribute_value", "attribute_name" : "attribute_value" },
    html: "innerHTML_content",
    children: [] //nested children are allowed
   }]
}
```

The `attribute_value` and `innerHTML_content` support **data replacement**.

Data in these strings is described in the following syntax: `$dataKey$`, where "dataKey" is the key of the data. The two ``$`` are required for data replacement to work.

---

`data` is an object holding the key/value of the data.

---

`config` is optional. You can change some configurations here.

- `strictReplace`: _ _boolean_ _ whether or not empty **data replacements** (missing the value in `data`) should be replaced with an empty string.

---

**You can find an example in [index.html](index.html).**


### Live Example

I used ElGen in my other projects. See [legendword/LVocab](https://github.com/legendword/LVocab) for an example.

