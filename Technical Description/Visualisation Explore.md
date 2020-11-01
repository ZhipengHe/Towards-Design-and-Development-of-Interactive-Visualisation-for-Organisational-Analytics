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
