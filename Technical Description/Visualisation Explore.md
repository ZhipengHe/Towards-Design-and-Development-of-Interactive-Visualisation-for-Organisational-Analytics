# Visualisation Methods

## 1. D3.js

### [1] What is D3.js

[D3.js](https://d3js.org/) is a **JavaScript** library for manipulating documents based on data. D3 helps you bring data to life using HTML, SVG, and CSS. D3’s emphasis on web standards gives you the full capabilities of modern browsers without tying yourself to a proprietary framework, combining powerful visualization components and a data-driven approach to DOM manipulation.

## 2. Vega

### [1] What is Vega

[Vega](https://vega.github.io/vega/) is a visualization grammar, a declarative language for creating, saving, and sharing interactive visualization designs. With Vega, you can describe the visual appearance and interactive behavior of a visualization in a **JSON** format, and generate web-based views using Canvas or SVG.

### [2] Vega and D3.js ([source](https://vega.github.io/vega/about/vega-and-d3/))

Comparing with D3.js, Vega:

- Support customizable designs.
- Make visualizations more reusable and shareable.
- Enable programmatic generation of visualizations.
- Improve performance and platform flexibility.

## 3. Vega-Lite

### [1] Different from Vega

[Vega-Lite](https://vega.github.io/vega-lite/) is a concise language for rapidly creating interactive visualizations. Vega-Lite specifications compile to full-blown Vega specifications. Though expressive and performant, Vega can still require verbose specifications: control flow is handled by the model, but the logic of event and data processing must be explicitly provided. As a result, Vega is not an ideal language for people to quickly author interactive plots in the midst of an analysis session. Vega-Lite focuses on rapid creation of common statistical graphics. Vega-Lite specifications are typically an order-of-magnitude smaller than corresponding Vega specifications. Compared to existing high-level grammars, Vega-Lite includes novel constructs for interaction techniques and multi-view displays.

### [2] Some Examples

#### Inline Data

![Inline Data](pic/Vega-Lite_Inline_Data.png)

Code:

```json
{
    "$schema": "https://vega.github.io/schema/vega-lite/v4.json",
    "data": {
        "values": [
            {"a": "C", "b": 2}, {"a": "C", "b": 7}, {"a": "C", "b": 4},
            {"a": "D", "b": 1}, {"a": "D", "b": 2}, {"a": "D", "b": 6},
            {"a": "E", "b": 8}, {"a": "E", "b": 4}, {"a": "E", "b": 7}
            ]
    },
    "mark": "bar",
    "encoding": {
        "y": {"field": "a", "type": "nominal"},
        "x": {
            "aggregate": "average", "field": "b", "type": "quantitative",
            "title": "Mean of b"
        }
    }
}
```

#### JSON by url

![JSON by url](pic/Vega-Lite_JSON_by_url.png)

```json
{
    "$schema": "https://vega.github.io/schema/vega-lite/v4.json",
    "data": {
        "url": "https://raw.githubusercontent.com/vega/vega/master/docs/data/cars.json"
    },
    "transform": [
        {
        "filter": {"field": "Cylinders", "lte": "5"}
        }
    ],
    "mark": "bar",
    "encoding": {
        "x": {"field": "Cylinders", "type": "quantitative"},
        "y": {"field": "Acceleration", "type": "quantitative"},
        "size": {"value": 20}
    }
}
```

The View-level `transform` object is an array of objects describing transformations.

#### Embed in HTML

To show Vega-Lite in websites, it could use Vega-Embed to create a DOM element for visualisation.

Use a content delivery network (CDN) to get the script.

```html
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@4"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
```
  
Here is the place for display the visualisation in HTML.

```html
<div id="visualisation"></div>
```

Then input Vega-Lite code in JavaScript.

```javascript
var vegaLiteCode = {
    // existing code omitted
};
```

Use Vega-Embed’s provided function to embed the code.

```javascript
// More argument info at https://github.com/vega/vega-embed
vegaEmbed('#visualisation', vegaLiteCode);
```

Here is an example by embdding the provious chart.

<iframe
  src="http://127.0.0.1:5500/Technical%20Description/data/vega-lite_embed.html"
  style="width:100%; height:270px;"
></iframe>
