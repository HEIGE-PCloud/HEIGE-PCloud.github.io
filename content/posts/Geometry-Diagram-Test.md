---
title: "Geometry Diagram Test"
date: 2021-02-17T16:44:11Z
tags: [Test]
draft: true
---

## GeoGebra Embed Webpage

<iframe src="https://www.geogebra.org/calculator/bhcnwtzy?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

## GeoGebra Local PNG Diagram

![](/images/Test%20GeoGebra.png)

## GeoGebra Local SVG Diagram

![](/images/Test%20GeoGebra.svg)

## Conclusion

For simple 2D geometry diagrams, I would expect to use some $\LaTeX$ packages such as [TikZ](https://www.overleaf.com/learn/latex/TikZ_package) to draw them. But apparently [KaTeX](https://katex.org/) does not support such function at the moment. So I choose to use [GeoGebra](https://www.geogebra.org/) for the painting job. The embed webpage is not working as I would expect, there seems no way to make the embed diagram readonly, and it significantly slows down the performance of the webpage, so I will not use that function. Comparing the PNG and SVG diagrams, the SVG format takes significant less storage space (9.86 KB) than the PNG format (234 KB) which makes the loading speed of the page faster. And as a vector graphics format, the SVG diagrams are lossless, which may increase the experience on a high resolution display. The only issue is that the diagrams generally have a white background, so they do not fit with the dark mode very well. Currently, this issue cannot be solved very easily.

In conclusion, all diagrams will be painted by GeoGebra and exported to a SVG file in the future.