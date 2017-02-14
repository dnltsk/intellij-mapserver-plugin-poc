#IntelliJ Mapserver Plugin (Proof of Concept)

plugin with some Mapserver/Mapfile editing features
[http://www.mapserver.org](http://www.mapserver.org)

## Mapfile language support

* Milestone 1: ordinary keyword highlighting
* Milestone 2: color preview/chooser for COLOR and BACKGROUNDCOLOR settings
* Milestone 3: Autocomplete
* Milestone 4: Schema errors like two WEB sections, duplicated layer names, incorrect scale denominations
* Milestone 5: Warnings, Autofixes

### possible solutions

1. parse Mapfile documentation for generate grammar and parser<br/>
http://www.mapserver.org/mapfile/map.html#map
2. describe Mapfile Syntax as JetBrain Meta Programming System (MPS)<br/>
https://www.jetbrains.com/mps/

### possible traps

1. tremendous efforts to implement
2. Mapserver version diversity
3. unspecific METADATA options
4. INCLUDE commands 

## WMS live-editing-preview

In general a preview area appears right beside the Mapfile text. Like we know it from a [Markdown plugin](https://github.com/vsch/idea-multimarkdown#rogues-gallery-of-features)

precondition: Mapserver is running on http://localhost and configured in IDEA

* Milestone 1: GetCapabilities preview
* Milestone 2: GetLegendGraphics preview (parameter: layer, scale)
* Milestone 3: GetMap preview (parameters: layer, tile id, tile size)
* Milestone 4: GetFeatureInfo preview (parameters: layer, tile id, tile size, click)

### possible solutions

1. configure running Mapserver URL via plugin settings dialog
2. configure target WMS version (and other settings) via plugin settings dialog
3. fire target request after every Mapfile modification 

### possible traps

1. tremendous efforts to implement
2. Mapserver version diversity

## WFS live-editing-preview

precondition: Mapserver is running on http://localhost and configured in IDEA

* Milestone 1: GetCapabilities preview
* Milestone 2: DescribeFeatureType preview
* ..

### possible solutions

see WMS live-editing-preview

### possible traps

see WMS live-editing-preview

## References

* IntelliJ Platform SDK DevGuide - Custom Language Support<br/>
http://www.jetbrains.org/intellij/sdk/docs/reference_guide/custom_language_support.html

* IntelliJ Platform SDK DevGuide - Custom Language Support Tutorial<br/>
http://www.jetbrains.org/intellij/sdk/docs/tutorials/custom_language_support_tutorial.html